# extraction
import java.util.List;
import twitter4j.Status;
import twitter4j.Twitter;
import twitter4j.TwitterException;
import twitter4j.TwitterFactory;
import twitter4j.conf.ConfigurationBuilder;


    
public class TwitterExtract {
	public static void main(String[] args) throws TwitterException {
	      ConfigurationBuilder cf = new ConfigurationBuilder();
	      
	      cf.setDebugEnabled(true)
	              .setOAuthConsumerKey("0zdsGq2SsCe3H77drEQRXLigj")
	              .setOAuthConsumerSecret("P5JBMqEVVmFiXfJv5te0npzKDAPUJaosNlW2MYp5RQpZzPR6PC")
	              .setOAuthAccessToken("4707760753-uO4jx4jkcZe56acBFb2zfq8Th7RxIaKzOeJg6jJ")
	              .setOAuthAccessTokenSecret("u5RvGB4JDjc5ZNXC9Lk5kQCqo7ROqisyqTFlqKpD6CdpX");
	      
	      TwitterFactory tf = new TwitterFactory(cf.build());
	    twitter4j.Twitter twitter = tf.getInstance();
	      
	        List<Status> status = twitter.getHomeTimeline();
	        for(Status st : status)
	        {
	            System.out.println(st.getUser().getName()+"--------"+st.getText());
	        }
	    }
	    
	}

