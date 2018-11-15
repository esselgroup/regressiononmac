package regression;

import static org.testng.Assert.assertTrue;

import java.util.Set;
import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.Dimension;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.Select;
import org.testng.Assert;
import org.testng.annotations.AfterClass;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.Test;

public class livingfoodz {
	//starting webdriver 
			WebDriver driver;
			@BeforeClass
			public void setup()
			{
				System.setProperty("webdriver.chrome.driver", "/Users/admin/Desktop/chromedriver");
				driver=new ChromeDriver();
				driver.manage().window().setSize(new Dimension(1600,900));
				driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
			}
			
			@AfterClass
			public void teardown(){
				driver.close();
				
			}
			
			@Test(priority=1)
			public void accessWebsite() {
				driver.get("https://livingfoodz.com");
				driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
				Assert.assertEquals(driver.getTitle(),"Tempting Food Recipes, Inviting Food Stories with Reviews - Living Foodz");
				}
			@Test(priority=2)
			public void facebookLogin() throws Exception{
				WebElement ele=driver.findElement(By.xpath("//*[@class='Fancy_button button--naira']"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click();", ele);
				Thread.sleep(1000);
				WebElement ele1= driver.findElement(By.xpath("//a[contains(@href,'https://livingfoodz.com/login/facebook')]"));
				JavascriptExecutor js1=(JavascriptExecutor)driver;
				js1.executeScript("arguments[0].click();", ele1);
				 driver.findElement(By.xpath("//*[@id=\"email\"]")).sendKeys("raviverma954@yahoo.com");
		         Thread.sleep(1000);
		         driver.findElement(By.xpath("//*[@id=\"pass\"]")).sendKeys("verma954ravi");
		         Thread.sleep(1000);
		         driver.findElement(By.xpath("//*[@id=\"pass\"]")).sendKeys(Keys.ENTER);
				 System.out.println("Login with fb is fine");
		     }
					         		
				@Test(priority=3)
				public void clickprofilelink(){
					driver.findElement(By.className("HeaderuserImg")).click();driver.getPageSource().contains("Ravi Ravjpoot");
					if(driver.getPageSource().contains("Ravi Rajpoot"))
					{System.out.println("Found Ravi Rajpoot");
					}
					
					
				}
				
				@Test(priority=4)
				public void homeFreshPics() throws InterruptedException {
					driver.get("https://livingfoodz.com");
					Thread.sleep(1000);
					String actual=driver.findElement(By.xpath("//*[contains(text(),'Fresh Picks')]")).getText();
					String expected="Fresh Picks";
					Assert.assertEquals(actual, expected);
					System.out.println("Fresh pics text is matched");
				}
				
						
				@Test(priority=5)
				public void homeRecipeOftheDay() {
					driver.findElement(By.linkText("Recipes of the Day")).isDisplayed();
				}
				
				@Test(priority=6)
				public void homeOurChefs() {
					String actual=driver.findElement(By.xpath("//span[contains(text(),'Our Chefs')]")).getText();
					String expected="Our Chefs";
					Assert.assertEquals(actual, expected);
					System.out.println(actual);
				}
				
				@Test(priority=7)
				public void homeTrendingOnLf() throws InterruptedException {
					String actual=driver.findElement(By.xpath("//span[contains(text(),'Trending on')]")).getText();
					String expected="Trending on";
					Assert.assertEquals(actual, expected);
					Thread.sleep(2000);
				}
				
				@Test(priority=8)
				public void homeAllShows() {
					String Actualtext=driver.findElement(By.xpath("//*[contains(text(),'All Shows')]")).getText();
					Assert.assertEquals(Actualtext, "View All Shows");
					System.out.println("All show text is matched");
				} 
				
				@Test(priority=9)
				public void recipeLanding1() {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[1]/a[1]")).click();
					driver.findElement(By.xpath("//*[@id=\"RecipeOfTheDay\"]/div/h2/span"));
				}
				
				@Test(priority=10)
				public void recipeRecipeOftheDay() {
					driver.findElement(By.xpath("//*[@id=\"RecipeOfTheDay\"]/div/h2/span")).isDisplayed();
				}
				
				@Test(priority=11)
				public void recipeOurChef() {
					driver.findElement(By.xpath("//*[contains(text(),'Our Chefs')]")).isDisplayed();
					System.out.println("Our chef list is displaying");
				}
				
				@Test(priority=12)
				public void recipeCusineType() {
					driver.findElement(By.linkText("Cuisine Types")).isDisplayed();
				}
				
				@Test(priority=13)
				public void recipeDetail() throws InterruptedException {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[1]/a[1]")).click();
					WebElement ele=driver.findElement(By.xpath("/html/body/section[1]/div/div[6]/div/div[2]/div[1]/div/div[2]/div[3]/a"));
					JavascriptExecutor js = (JavascriptExecutor)driver;
			        js.executeScript("arguments[0].click();", ele);
			        System.out.println("recipe detail on card click");
			        driver.get("https://livingfoodz.com/recipes/detail/Thattai-388");
				    //Recipe name
				    driver.findElement(By.xpath("//*[@class='text-left' and contains (text(),'Thattai')]")).isDisplayed();
				    System.out.println("recipe name is correct");
				    driver.findElement(By.linkText("Gautam Mehrishi")).isDisplayed();
				    System.out.println("chefname available");
				    //About chef
				    String Actual=driver.findElement(By.xpath("//*[@class='HeadingTextCenter' and contains (text(),'Meet the people behind the luscious food, delicious recipes and entertaining shows')]")).getText();
				    String expected="Meet the people behind the luscious food, delicious recipes and entertaining shows";
				    Assert.assertEquals(Actual, expected);
				    System.out.println(Actual);
				    //Chef's recipe
				    String Actual1=driver.findElement(By.xpath("//span[contains(text(),'Chef Recipes')]")).getText();
				    String expected1="Chef Recipes";
				    Assert.assertEquals(Actual1, expected1);
				    System.out.println("Chef Recipe Section is Available");
				    //Similar Recipes
				    /*String similarRecipe=driver.findElement(By.xpath("//span[contains(text(),'Similar Recipes')]")).getText();
				    String expactersr="Similar Recipes";
				    Assert.assertEquals(similarRecipe, expactersr);
				    System.out.println("Similar Recipe available");*/
				    String youmaylike=driver.findElement(By.xpath("//*[@class='ob-widget-header']")).getText();
				    String expectedobtxt="Promoted Stories";
				    Assert.assertEquals(youmaylike, expectedobtxt);
				    System.out.println(youmaylike);
				}
				
				@Test(priority=14)
				public void recipeDetailComments() {
					String parentWindow = driver.getWindowHandle();
					Set<String> handles =  driver.getWindowHandles();
					   for(String windowHandle  : handles)
					       {
					       if(!windowHandle.equals(parentWindow))
					          {
					          driver.switchTo().window(windowHandle);
					          
					        // <!--Perform your operation here for new window-->
					          //closing child window
					          driver.findElement(By.xpath("//*[@id=\"facebook\"]/body/div/div/div/div/div/div[2]/div[2]/div/div/div[1]/div[1]/div/div/div[2]/div/div/div/div")).sendKeys("NICE!!");;
					          driver.findElement(By.xpath("//*[@id=\"facebook\"]/body/div/div/div/div/div/div[2]/div[2]/div/div/div[2]/div/div[2]/span/button")).click();
					         driver.switchTo().window(parentWindow);}}
				}
						
				@Test(priority=15)
				public void showLanding1() throws Exception {
					driver.findElement(By.xpath("//a[contains(@href,'https://livingfoodz.com/shows')]")).click();
					Thread.sleep(1000);
				}
				
				@Test(priority=16)
				public void showOnLf() {
					String showOnLF=driver.findElement(By.xpath("//span[contains(text(),'Shows on')]")).getText();
					String expactedslf="Shows on";
					Assert.assertEquals(showOnLF, expactedslf);	
					System.out.println(showOnLF);
					}
				
				@Test(priority=17)
				public void showOurHosts() {
					String ourHosts=driver.findElement(By.xpath("//span[contains(text(),'Our Hosts')]")).getText();
					String expactedsOR="Our Hosts";
					Assert.assertEquals(ourHosts, expactedsOR);	
					System.out.println(ourHosts);
					
				}
				
				@Test(priority=18)
				public void showTrendingOnLF() {
					driver.findElement(By.xpath("//*[@id=\"TrendingOn\"]/div/h2/span")).isDisplayed();
				}
				
				@Test(priority=19)
				public void peopleLanding() {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[3]/a[1]")).click();
				}
				
				@Test(priority=20)
				public void peopleChefHost() {
					driver.findElement(By.linkText("Chefs & Hosts")).isDisplayed();
				}
				
				@Test(priority=21)
				public void peopleScoops() throws Exception {
					driver.findElement(By.xpath("//*[@id=\"Scoops\"]/div/h2/span")).isDisplayed();
					Thread.sleep(1000);
				}
				
				@Test(priority=22)
				public void ChefProfile() throws Exception {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[3]/a[1]")).click();
					WebElement ele=driver.findElement(By.xpath("//*[@id=\"chef_9\"]/div/div/div/div[2]/a"));
					JavascriptExecutor js=(JavascriptExecutor)driver;
					js.executeScript("arguments[0].click()", ele);
					String aboutChef=driver.findElement(By.xpath("//*[preceding-sibling::h2 = 'Rakhee Vaswani']")).getText();
					String expacted="Chef";
					Assert.assertEquals(aboutChef, expacted);
					System.out.println(expacted);
				}
				
				@Test(priority=23)
				public void ChefProfileRecipeByChef() {
					String recipeByChef=driver.findElement(By.xpath("//span[contains(text(),'Recipes by Chef')]")).getText();
					String expectedrbchef="Recipes by Chef";
					Assert.assertEquals(recipeByChef, expectedrbchef);
					System.out.println("Recipes are available");
					}
				
				@Test(priority=24)
				public void ChefProfileFBComments() {
					String parentWindow = driver.getWindowHandle();
					Set<String> handles =  driver.getWindowHandles();
					   for(String windowHandle  : handles)
					       {
					       if(!windowHandle.equals(parentWindow))
					          {
					          driver.switchTo().window(windowHandle);
					          
					        // <!--Perform your operation here for new window-->
					          //closing child window
					          driver.findElement(By.xpath("//*[@id=\"facebook\"]/body/div/div/div/div/div/div[2]/div[2]/div/div/div[1]/div[1]/div/div/div[2]/div/div/div/div")).sendKeys("NICE!!");;
					          driver.findElement(By.xpath("//*[@id=\"facebook\"]/body/div/div/div/div/div/div[2]/div[2]/div/div/div[2]/div/div[2]/span/button")).click();
					         driver.switchTo().window(parentWindow);}
				}
			}
				
						
				@Test(priority=26)
				public void chefProfileOurChefs() {
					String actual=driver.findElement(By.xpath("//span[contains(text(),'Our Chefs')]")).getText();
					String expected="Our Chefs";
					Assert.assertEquals(actual, expected);
					System.out.println(actual);
				}
				
				@Test(priority=27)
				public void storyLanding(){
					WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[4]/a[1]"));
					Actions act=new Actions(driver);
					act.moveToElement(ele).click().perform();
				}
				
				@Test (priority=28)
				public void storyDishup() {
					driver.findElement(By.xpath("//*[contains(text(),'Dish Up')]")).isDisplayed();
					System.out.println("DishUp Category is displaying");
				}
				
				@Test(priority=29)
				public void storyPopCulture() {
					driver.findElement(By.xpath("//*[contains(text(),'Pop Culture')]")).isDisplayed();
					System.out.println("PopCulture category is displaying");
				}
				
				@Test(priority=30)
				public void storyPlaces() {
					driver.findElement(By.linkText("Places")).isDisplayed();
				}
				
				@Test(priority=31)
				public void storyEntertainment() {
					driver.findElement(By.linkText("Entertainment")).isDisplayed();
				}
				
				@Test(priority=32)
				public void storyFoodplusplus() {
					driver.findElement(By.linkText("Food++")).isDisplayed();
				}
				
				@Test(priority=33)
				public void storyHealth() {
					driver.findElement(By.linkText("Health")).isDisplayed();
				}
				
				@Test(priority=34)
				public void reviewLanding() {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[5]/a[1]")).click();			
				}
				
				@Test(priority=35)
				public void reviewMumbai() {
					driver.findElement(By.linkText("Mumbai")).isDisplayed();
				}
				
				@Test(priority=36)
				public void reviewDelhi() {
					driver.findElement(By.linkText("Delhi")).isDisplayed();
				}
				
				@Test(priority=37)
				public void reviewBangalore() {
					driver.findElement(By.linkText("Bangalore")).isDisplayed();
				}
				
				@Test(priority=38)
				public void reviewPune() {
					driver.findElement(By.linkText("Pune")).isDisplayed();
				}
				
				@Test(priority=39)
				public void reviewOther() {
					driver.findElement(By.linkText("Other")).isDisplayed();
				}
				
				@Test(priority=40)
				public void howTo() {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[6]/a[1]")).click();			
				}
				
				@Test(priority=41)
				public void howToKitchenHacks() {
					driver.findElement(By.linkText("Kitchen Hacks")).isDisplayed();
				}
				
				@Test(priority=42)
				public void howToTipsandTricks() {
					String actual=driver.findElement(By.xpath("//span[contains(text(),'Tips & Tricks')]")).getText();
					String expected="Tips & Tricks";
					Assert.assertEquals(actual, expected);
					System.out.println(actual);
				}
				
				@Test(enabled=false)
				public void awards() throws InterruptedException {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[7]/a")).click();
					Thread.sleep(3000);
				}
				
				@Test(enabled=false)
				public void awardsAbout() {
					driver.findElement(By.xpath("//*[@id=\"about_section1\"]/div/div/div[2]/div/h1")).isDisplayed();			
				}
				
				@Test(enabled=false)
				public void awardsCategories() {
					WebElement Elem = driver.findElement(By.xpath("//*[@id=\"page-top\"]/web-app/app-events/app-index-guild-award/app-guild-awards-menu/div[1]/div/div/ul/li[2]/a"));
					Actions act= new Actions (driver);
					act.moveToElement(Elem).click().perform();
				}
				
				@Test(enabled=false)
				public void awardsFoodInsta() {
					WebElement Ele= driver.findElement(By.xpath("//*[@id=\"page-top\"]/web-app/app-events/app-guild-awards-categories/app-guild-awards-menu/div[1]/div/div/ul/li[3]/a"));			
					Actions act= new Actions(driver);
					act.moveToElement(Ele).click().perform();
				}
				
				@Test(enabled=false)
				public void awardsEnteratiner() {
					WebElement Ele= driver.findElement(By.xpath("//*[@id=\"page-top\"]/web-app/app-events/app-guild-awards-food-instagrammer/app-guild-awards-menu/div[1]/div/div/ul/li[4]/a"));			
					Actions act= new Actions(driver);
					act.moveToElement(Ele).click().perform();
				}
				
				@Test(enabled=false)
				public void awards2017Winners() {
					WebElement Ele= driver.findElement(By.xpath("//*[@id=\"page-top\"]/web-app/app-events/app-guild-awards-food-entertainer/app-guild-awards-menu/div[1]/div/div/ul/li[7]/a"));			
					Actions act= new Actions(driver);
					act.moveToElement(Ele).click().perform();
				}
				
						
				@Test(priority=49)
				public void showDetails() throws Exception {
					driver.get("https://livingfoodz.com/shows/detail/Northen-Flavours-Season-2-32");
					Thread.sleep(2000);
				}
				
				@Test(priority=50)
				public void showdetailTitle() {
					
					String actual=driver.findElement(By.xpath("//*[@class='Show_detail_HeadingRewind Show_detail_HeadingRewind2']")).getText();
					String expected="Northen Flavours Season 2";
					Assert.assertEquals(actual, expected);
					System.out.println(actual);
					
				}	
				
				@Test(priority=51)
				public void showdetailDescription() {
					String actual=driver.findElement(By.xpath("//*[@class='Show_detail_HeadingDescription']")).getText();
					String expected=actual;
					Assert.assertEquals(actual, expected);
					System.out.println(actual);
					
				}
				
				@Test(priority=52)
				public void showdetailComments() {
					String parentWindow = driver.getWindowHandle();
					Set<String> handles =  driver.getWindowHandles();
					   for(String windowHandle  : handles)
					       {
					       if(!windowHandle.equals(parentWindow))
					          {
					          driver.switchTo().window(windowHandle);
					          
					        // <!--Perform your operation here for new window-->
					          //closing child window
					          driver.findElement(By.xpath("//*[@id=\"facebook\"]/body/div/div/div/div/div/div[2]/div[2]/div/div/div[1]/textarea")).sendKeys("NICE!!");;
					          
					         driver.switchTo().window(parentWindow);}}
				}
				
				@Test(priority=53)
				public void showdetailAboutHost() {
						String actual=driver.findElement(By.xpath("//*[@class='fancy_Heading']")).getText();
						String expected="About Host";
						Assert.assertEquals(actual, expected);
						System.out.println(actual);
						
					}
					
				
				@Test(priority=54)
				public void showdetailArticleAboutShow() {
					String actual=driver.findElement(By.xpath("//span[contains(text(),'Our Chefs')]")).getText();
					String expected="Our Chefs";
					Assert.assertEquals(actual, expected);
					System.out.println(actual);
					
				}
				
				@Test(priority=55)
				public void showdetailOurHosts() throws Exception {
					String actual=driver.findElement(By.xpath("//span[contains(text(),'Our Chefs')]")).getText();
					String expected="Our Chefs";
					Assert.assertEquals(actual, expected);
					System.out.println(actual);
					Thread.sleep(2000);
				}
				
				@Test(priority=56)
				public void showdetail_All_Shows() {
					String actual=driver.findElement(By.xpath("//span[contains(text(),'All Shows')]")).getText();
					String expected="All Shows";
					Assert.assertEquals(actual, expected);
					System.out.println(actual);
				}
				
				@Test(priority=58)
				public void storyDetail() throws Exception {
					driver.get("https://livingfoodz.com/stories/Sweet-Treats-for-Those-Who-Want-to-Stay-off-Butter-and-Ghee-134");
					Thread.sleep(1000);
				}
				
				@Test(priority=59)
				public void storyDetailTitle() throws Exception {
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/div/div/div[3]/div/h1")).isDisplayed();
					Thread.sleep(1000);
				}
				
				@Test(priority=60)
				public void storyDetailRelatedStories() throws Exception {
					String actual=driver.findElement(By.xpath("//*[contains(text(),'Related Stories')]")).getText();
					String expected="Related Stories";
					Assert.assertEquals(actual, expected);
					System.out.println(actual);
					Thread.sleep(1000);
				}
						
					
				@Test(priority=65)
				public void storyDetailsComments() {
					
				String parentWindow = driver.getWindowHandle();
				Set<String> handles =  driver.getWindowHandles();
				   for(String windowHandle  : handles)
				       {
				       if(!windowHandle.equals(parentWindow))
				          {
				          driver.switchTo().window(windowHandle);
				          
				        // <!--Perform your operation here for new window-->
				          //closing child window
				          driver.findElement(By.xpath("//*[@id=\"facebook\"]/body/div/div/div/div/div/div[2]/div[2]/div/div/div[1]/div[1]/div/div/div[2]/div/div/div/div")).sendKeys("NICE!!");;
				          driver.findElement(By.xpath("//*[@id=\"facebook\"]/body/div/div/div/div/div/div[2]/div[2]/div/div/div[2]/div/div[2]/span/button")).click();
				         driver.switchTo().window(parentWindow);}}
			}
						
				@Test(enabled=false)
				public void awardsTicketsbookinglink() throws Exception {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[7]/a")).click();
					Thread.sleep(2000);
				}
				
				@Test(enabled=false)
				public void awardBuzz() throws Exception {
					driver.findElement(By.xpath("//*[@id=\"page-top\"]/web-app/app-events/app-index-guild-award/app-guild-awards-menu/div[1]/div/div/ul/li[5]/a")).click();;
					Thread.sleep(1000);
							
				}
				
				@Test(priority=69)
				public void search() throws InterruptedException {
					WebElement ele=driver.findElement(By.xpath("//*[@id=\"mainNav\"]/div/div[2]/a/img[1]"));
					Actions act=new Actions(driver);
					act.moveToElement(ele).click().perform();
					driver.findElement(By.id("searchTextValue")).sendKeys("Chicken");
					driver.findElement(By.id("searchTextValue")).sendKeys(Keys.ENTER);
					Thread.sleep(1000);
				}   
				
				@Test(priority=70)
				public void BackfromStoryDetail() throws InterruptedException {
					WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[4]/a[1]"));
					Actions act=new Actions(driver);
					act.moveToElement(ele).click().perform();
					driver.findElement(By.xpath("//*[@class='carouselCoverImage']")).click();
					driver.findElement(By.xpath("//a[@href='javascript:void(0);']")).click();
					System.out.println("Back button on story detail working fine");
					Thread.sleep(2000);
				}
				
				@Test(priority=71)
				public void homeCarousel() throws Exception {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/div[1]/a")).click();
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
				}
				
				@Test(priority=72)
				public void recipeCarousel() throws Exception {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[1]/a[1]")).click();
					driver.findElement(By.xpath("//*[@id=\"RecipeOfTheDay\"]/div/h2/span"));
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/div[1]/a")).click();
					Thread.sleep(500);
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
				}
				
				@Test(priority=73)
				public void showCarousel() throws Exception {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[2]/a[1]")).click();
					Thread.sleep(500);
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
				}
				
				@Test(priority=74)
				public void peopleCarousel() throws Exception {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[3]/a[1]")).click();
					Thread.sleep(500);
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
				}
				
				@Test(priority=75)
				public void storyCarousel() throws Exception{
					WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[4]/a[1]"));
					Actions act=new Actions(driver);
					act.moveToElement(ele).click().perform();
					Thread.sleep(500);
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
				}
				
				@Test(priority=76)
				public void reviewCarousel() throws Exception {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[5]/a[1]")).click();
					Thread.sleep(500);
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
				}
				
				@Test(priority=77)
				public void howToCarousel() throws Exception {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[6]/a[1]")).click();
					Thread.sleep(500);
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
					driver.findElement(By.xpath("//*[@id=\"carousel-example-generic\"]/a[2]")).click();
					Thread.sleep(500);
				}
				
				@Test(enabled=false)//Its removed from frontend
				public void recipeOnCardTagRedirection() throws InterruptedException {
					driver.get("https://livingfoodz.com/recipes/");
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[1]/a[1]")).click();
					driver.findElement(By.xpath("//*[@id=\"RecipeOfTheDay\"]/div/h2/span"));
					WebElement ele=driver.findElement(By.xpath("//*[@id=\"RecipesMenu1\"]/div[2]/div/div[2]/div[1]/div[1]/a/h3"));
					JavascriptExecutor js = (JavascriptExecutor)driver;
			        js.executeScript("arguments[0].click();", ele);
				    Thread.sleep(3000);
				}
				
				@Test(enabled=false)
				public void recipeOnCardTitleRedirection() throws InterruptedException {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[1]/a[1]")).click();
					driver.findElement(By.xpath("//*[@id=\"RecipeOfTheDay\"]/div/h2/span"));
					WebElement ele=driver.findElement(By.xpath("//*[@id=\"RecipesMenu1\"]/div[1]/div/div[2]/div[1]/h4/a"));
					JavascriptExecutor js = (JavascriptExecutor)driver;
			        js.executeScript("arguments[0].click();", ele);
				    Thread.sleep(3000);
				}
				
				@Test(enabled=false)
				public void recipeOnCardDecRedirection() throws InterruptedException {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[1]/a[1]")).click();
					driver.findElement(By.xpath("//*[@id=\"RecipeOfTheDay\"]/div/h2/span"));
					WebElement ele=driver.findElement(By.xpath("//*[@id=\"RecipesMenu1\"]/div[1]/div/div[2]/div[1]/p/a"));
					JavascriptExecutor js = (JavascriptExecutor)driver;
			        js.executeScript("arguments[0].click();", ele);
				    Thread.sleep(3000);
				}
				
				@Test(enabled=false)
				public void recipeOnCardChefRedirection() throws InterruptedException {
					driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[1]/a[1]")).click();
					driver.findElement(By.xpath("//*[@id=\"RecipeOfTheDay\"]/div/h2/span"));
					WebElement ele=driver.findElement(By.xpath("//*[@id=\"RecipesMenu1\"]/div[1]/div/div[2]/div[1]/div[4]/div[2]/h5/a"));
					JavascriptExecutor js = (JavascriptExecutor)driver;
			        js.executeScript("arguments[0].click();", ele);
				    Thread.sleep(3000);
				}
				
				@Test(priority=82)
				public void recipeSublinksRecipeOfTheDay() throws Exception {
				driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[1]/a[1]")).click();
				driver.findElement(By.xpath("//*[@id=\"RecipeOfTheDay\"]/div/h2/span"));
				Thread.sleep(1000);
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[1]/ul/li[1]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=83)
			public void recirecipeSublinksCusineType() throws Exception {
			WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[1]/ul/li[2]/a"));
			JavascriptExecutor js=(JavascriptExecutor)driver;
			js.executeScript("arguments[0].click()", ele);
			Thread.sleep(1000);
		}
			
			@Test(priority=84)
			public void recirecipeSublinksOurChef() throws Exception {
			WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[1]/ul/li[3]/a"));
			JavascriptExecutor js=(JavascriptExecutor)driver;
			js.executeScript("arguments[0].click()", ele);
			Thread.sleep(1000);
		}
			
			@Test(priority=85)
			public void showSubLinkShowOnLF() throws Exception {
				driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[2]/a[1]")).click();
				Thread.sleep(1000);
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[2]/ul/li[1]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=86)
			public void showSubLinkChefHost() throws Exception {
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[2]/ul/li[2]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(enabled=false)
			public void showSubLinkTrendingonLF() throws Exception {
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[2]/ul/li[3]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=88)
			public void PeopleSubLinkChefandHost() throws Exception {
				driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[3]/a[1]")).click();
				Thread.sleep(1000);
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[3]/ul/li[1]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=89)
			public void PeopleSubLinkScoop() throws Exception {
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[3]/ul/li[2]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=90)
			public void StorySublinkDishUp() throws Exception {
				WebElement ele1=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[4]/a[1]"));
				Actions act1=new Actions(driver);
				act1.moveToElement(ele1).click().perform();
				Thread.sleep(1000);
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[4]/ul/li[1]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=91)
			public void StorySublinkPopCulture() throws Exception {
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[4]/ul/li[2]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=92)
			public void StorySublinkPlace() throws Exception {
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[4]/ul/li[3]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=93)
			public void StorySublinkEntertainment() throws Exception {
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[4]/ul/li[4]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=94)
			public void StorySublinkFood() {
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[4]/ul/li[5]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
			}
			
			@Test(priority=95)
			public void StorySublinkHealth() throws Exception {
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[4]/ul/li[6]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=96)
			public void reviewSubLinkMumbai() throws Exception {
				driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[5]/a[1]")).click();
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[5]/ul/li[1]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=97)
			public void reviewSubLinkDelhi() throws Exception {
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[5]/ul/li[2]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=98)
			public void reviewSubLinkBangalore() throws Exception {
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[5]/ul/li[3]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=99)
			public void reviewSubLinkPune() throws Exception {
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[5]/ul/li[4]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=100)
			public void reviewSubLinkOther() throws Exception {
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[5]/ul/li[5]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=101)
			public void HowToSubLinkKitchenHacks() throws Exception {
				driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[6]/a[1]")).click();
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[6]/ul/li[1]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(1000);
			}
			
			@Test(priority=102)
			public void HowToSubLinkTipsTricks() throws Exception {
				WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[6]/ul/li[2]/a"));
				JavascriptExecutor js=(JavascriptExecutor)driver;
				js.executeScript("arguments[0].click()", ele);
				Thread.sleep(2000);
			}
				
			@Test(priority=103)
			public void aboutLF() throws Exception {
				driver.findElement(By.xpath("//a[contains(@href,'https://livingfoodz.com/about')]")).click();
				Thread.sleep(2000);
				Assert.assertEquals(driver.getCurrentUrl(), "https://livingfoodz.com/about");
				System.out.println("About us page is displaying");
				
			}
			
			@Test(priority=104)
			public void termsOfUse() {
				driver.findElement(By.xpath("//a[contains(@href,'https://livingfoodz.com/terms')]")).click();
				Assert.assertEquals(driver.getCurrentUrl(), "https://livingfoodz.com/termsofuse");
				System.out.println("T&C displaying");
			}
			
			
			@Test(priority=105)
			public void stayConnectedTwitter() throws Exception {
				driver.findElement(By.xpath("//img[@src='https://livingfoodz.com/assets/images/twitter__footer.png']")).click();
				String parentWindow = driver.getWindowHandle();
				Set<String> handles =  driver.getWindowHandles();
				   for(String windowHandle  : handles)
				       {
				       if(!windowHandle.equals(parentWindow))
				          {
				          driver.switchTo().window(windowHandle);
				          Thread.sleep(1000);
				          System.out.println("LF Twitter URL is opened");
				          driver.switchTo().window(parentWindow); //cntrl to parent window
				          
				         Thread.sleep(1000);
				         
				          }
				       }
			}
			
			@Test(priority=106)
			public void stayConnectedInsta() throws Exception {
				driver.findElement(By.xpath("//img[@src='https://livingfoodz.com/assets/images/instagram_footer.png']")).click();
				String parentWindow = driver.getWindowHandle();
				Set<String> handles =  driver.getWindowHandles();
				   for(String windowHandle  : handles)
				       {
				       if(!windowHandle.equals(parentWindow))
				          {
				          driver.switchTo().window(windowHandle);
				          Thread.sleep(1000);
				          System.out.println("LF Insta URL is opened");
				          driver.switchTo().window(parentWindow); //cntrl to parent window
				          System.out.println();
				         Thread.sleep(1000);
				         
				          }
				       }
			}
			
			
			@Test(priority=107)
			public void stayConnectedFacebook() throws Exception {
				driver.findElement(By.xpath("//img[@src='https://livingfoodz.com/assets/images/fb_footer.png']")).click();
				String parentWindow = driver.getWindowHandle();
				Set<String> handles =  driver.getWindowHandles();
				   for(String windowHandle  : handles)
				       {
				       if(!windowHandle.equals(parentWindow))
				          {
				          driver.switchTo().window(windowHandle);
				          Thread.sleep(1000);
				          System.out.println("LF Facebook URL is opened");
				          driver.switchTo().window(parentWindow); //cntrl to parent window
				          System.out.println();
				         Thread.sleep(1000);
				         
				          }
				       }
			}
				@Test (enabled=false)
				public void nextStory() throws Exception {
					WebElement ele=driver.findElement(By.xpath("//*[@id=\"main-nav\"]/ul/li[4]/a[1]"));
					Actions act=new Actions(driver);
					act.moveToElement(ele).click().perform();
					Thread.sleep(2000);
					WebElement ele1=driver.findElement(By.xpath("//*[@id=\"slider_dish_up\"]/div/div/div[5]/div/div/div/div[2]/div[3]/a"));
					JavascriptExecutor js=(JavascriptExecutor)driver;
					js.executeScript("arguments[0].click();", ele1);
					Thread.sleep(1000);
					js.executeScript("window.scrollBy(0,10200)");
					Thread.sleep(2000);
					driver.findElement(By.linkText("Next Story")).isDisplayed();
					Thread.sleep(1000);
				}
				
				
				
				@Test (priority=109)
				public void reTargetting() {
					String ps = driver.getPageSource();
					assertTrue(ps.contains("var google_conversion_id = 808504411;"));
				}
				
				@Test (priority=110)
				public void faceBookCode() {
					String ps = driver.getPageSource();
					assertTrue(ps.contains("fbq('init', '364424560719749');"));
				}
				
				@Test (priority=111)
				public void crazyEgg() {
					String ps = driver.getPageSource();
					assertTrue(ps.contains("src=\"//script.crazyegg.com/pages/scripts/0074/1182.js"));
				}
				
				@Test(enabled=false)
				public void UCG() throws Exception{
				driver.findElement(By.cssSelector(".navbar-brand")).click();
				driver.findElement(By.linkText("Click here to Share your Recipe")).click();
				Thread.sleep(2000);
				driver.findElement(By.id("name")).sendKeys("UCG content for test purpose");
				Thread.sleep(1000);
				Select category=new Select (driver.findElement(By.id("category")));
				category.selectByValue("nonveg");
				Thread.sleep(1000);
				driver.findElement(By.id("description")).sendKeys("These pancakes will definitely satisfy your rumbling tummy. Try this simple recipe of besan combined with onion and tomato.mmmmmmmmmmmmmmmmmmmmmmm");
				Thread.sleep(1000);
				Select cuisine=new Select (driver.findElement(By.id("cuisine")));
				cuisine.selectByValue("asian");
				Thread.sleep(1000);
				Select serving=new Select(driver.findElement(By.id("serving")));
				serving.selectByValue("4");
				Thread.sleep(1000);
				Select CookingTime=new Select(driver.findElement(By.id("CookingTime")));
				CookingTime.selectByValue("20 Min");
				Thread.sleep(1000);
				Select type=new Select(driver.findElement(By.id("type")));
				type.selectByValue("beverage");
				Thread.sleep(1000);
				Actions Imageupload= new Actions(driver);
				Imageupload.moveToElement(driver.findElement(By.xpath("//*[@class='input-group-btn browse_Btn']"))).doubleClick().perform();
				Thread.sleep(2000);
				Runtime.getRuntime().exec("C:\\Users\\ravindra.kumar.ZEE\\Desktop\\clicknupload.exe");
				Thread.sleep(1000);
				System.out.println("Image is uploaded");
				Thread.sleep(5000);
				Actions add=new Actions(driver);
				add.moveToElement(driver.findElement(By.cssSelector("div.col-md-1:nth-child(2) > img:nth-child(1)"))).doubleClick().perform();
				Thread.sleep(1000);
				add.moveToElement(driver.findElement(By.cssSelector("div.col-md-1:nth-child(3) > img:nth-child(1)"))).doubleClick().perform();
				Thread.sleep(1000);
				Thread.sleep(1000);
				driver.findElement(By.xpath("/html/body/web-app/app-users/app-user-generated-recipes/section/div[2]/form/div[3]/div[6]/div[2]/div[1]/div[1]/div[1]/input")).sendKeys("300 gm firm tofu, sliced");
				Thread.sleep(1000);
				driver.findElement(By.xpath("/html/body/web-app/app-users/app-user-generated-recipes/section/div[2]/form/div[3]/div[6]/div[2]/div[2]/div[1]/div[1]/input")).sendKeys("2 tbsp lemongrass, chopped");
				Thread.sleep(1000);
				driver.findElement(By.xpath("/html/body/web-app/app-users/app-user-generated-recipes/section/div[2]/form/div[3]/div[6]/div[2]/div[3]/div[1]/div[1]/input")).sendKeys("1 2 tsp parsley, chopped");
				Thread.sleep(1000);
				System.out.println("Cuisine added");
				Thread.sleep(2000);
				Actions addsteps=new Actions(driver);
				addsteps.moveToElement(driver.findElement(By.cssSelector("div.col-md-1:nth-child(4) > img:nth-child(1)"))).doubleClick().perform();
				Thread.sleep(1000);
				addsteps.moveToElement(driver.findElement(By.cssSelector("div.col-md-1:nth-child(4) > img:nth-child(1)"))).doubleClick().perform();
				Thread.sleep(1000);
				addsteps.moveToElement(driver.findElement(By.cssSelector("div.col-md-1:nth-child(4) > img:nth-child(1)"))).doubleClick().perform();
				driver.findElement(By.xpath("/html/body/web-app/app-users/app-user-generated-recipes/section/div[2]/form/div[3]/div[11]/div[2]/div[1]/div[1]/div[1]/input")).sendKeys("Slice the tofu into fine medium pieces.");
				Thread.sleep(1000);
				driver.findElement(By.xpath("/html/body/web-app/app-users/app-user-generated-recipes/section/div[2]/form/div[3]/div[11]/div[2]/div[2]/div[1]/div[1]/input")).sendKeys("Heat oil in a pan and shallow fry the slices on both sides.");
				Thread.sleep(1000);
				driver.findElement(By.xpath("/html/body/web-app/app-users/app-user-generated-recipes/section/div[2]/form/div[3]/div[11]/div[2]/div[3]/div[1]/div[1]/input")).sendKeys("Drain excess oil.");
				System.out.println("steps added");
				Thread.sleep(3000);
				Actions publish=new Actions(driver);
				publish.moveToElement(driver.findElement(By.cssSelector(".button1"))).doubleClick().perform();
				Thread.sleep(4000);
			    driver.switchTo().activeElement();
			    Thread.sleep(1000);
			    String actual=driver.findElement(By.cssSelector("div.modal-body:nth-child(2) > p:nth-child(1)")).getText();
			    String expected="Congratulations, weíve received your recipe. You can view it shortly.";
			    Assert.assertEquals(actual, expected);
			    System.out.println(actual);
			    Thread.sleep(2000);
				driver.findElement(By.cssSelector("div.modal-footer:nth-child(3) > button:nth-child(1)")).click();
			}
			
				
				
				
			//Third party tool to test the image size
				/*@Test(priority=200)
			    public void imageSizeShouldBeInKBs() throws InterruptedException {
				System.setProperty("webdriver.chrome.driver", "D:\\Automation\\chromedriver.exe");
				WebDriver driver = new ChromeDriver();
				driver.get("https://www.giftofspeed.com/image-delivery/index.php?");
				driver.findElement(By.xpath("/html/body/section[1]/div[2]/div/form/div[1]/div[1]/input")).sendKeys(Keys.CONTROL,"a",Keys.DELETE);
				driver.findElement(By.xpath("/html/body/section[1]/div[2]/div/form/div[1]/div[1]/input")).sendKeys("http://livingfoodz.in");
				driver.findElement(By.xpath("//*[@id=\"submit\"]")).click();
				}*/

		}	


