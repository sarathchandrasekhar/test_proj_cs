# test_proj_cs
package mytestngpackage;

import junit.framework.Assert;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.Test;

public class MyTestNGfile 
{
  
	public String RedHatUrl = "https://uat-red-hat-training-roi.webappuat.com/";
	
	WebDriver rh = new FirefoxDriver();
	
	
	@SuppressWarnings("deprecation")
	@Test
  public void verifyHomePage() throws InterruptedException
  {
		//launch red hat
		rh.get(RedHatUrl);
		
		String expectedTitle = "Interactive Infographic";
		String actualTitle = rh.getTitle();
		
		Assert.assertEquals(expectedTitle, actualTitle);
		
		//click modal OK		
       rh.get("https://uat-red-hat-training-roi.webappuat.com/");
		
		rh.manage().window().maximize();
		
		rh.findElement(By.xpath(".//*[@id='disclaimerModal']/div/div/div[2]/a")).click();
		
		rh.findElement(By.xpath(".//*[@id='submitquestionnaire']")).click();
		
		rh.findElement(By.xpath(".//*[@id='Questionnaire']/div/div/div/div[1]/div[2]/div[1]/div/label")).sendKeys("IDC Tesh Sch");
		
		//employee size
		// 2. Number of employees
		  rh.findElement(By.xpath(".//*[@id='employeeCount']")).sendKeys("2");
 
		
  }
}
