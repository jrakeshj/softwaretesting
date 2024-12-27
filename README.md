import java.io.File;

import java.io.IOException;

import org.apache.commons.io.FileUtils;

import org.openqa.selenium.By;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import org.openqa.selenium.support.ui.Select;
import org.openqa.selenium.TakesScreenshot;


public class Day100 {
	public static void main(String[] args ) throws InterruptedException, IOException
	
	{
		 WebDriver driver= new ChromeDriver();
		 
		 driver.get("https://adactinhotelapp.com/BookHotel.php");
		 driver.manage().window().maximize();
		
		driver.findElement(By.xpath("//*[@id=\"username\"]")).sendKeys("Rakesh23032000");
		driver.findElement(By.xpath("//*[@id=\"password\"]")).sendKeys("Rake@18230");
		driver.findElement(By.xpath("//*[@id=\"login\"]")).click();

		
		Thread.sleep(7000);
		WebElement y= driver.findElement(By.id("location"));
		Select s = new Select(y);
		s.selectByValue("Brisbane");
		Thread.sleep(7000);
		WebElement z= driver.findElement(By.id("hotels"));
		Select s1=new Select(z);
		s1.selectByIndex(1);
		WebElement x= driver.findElement(By.id("room_type"));
		Select s2=new Select(x);
		s2.selectByIndex(2);
		WebElement a=driver.findElement(By.id("room_nos"));
		Select s3=new Select(a);
		s3.selectByIndex(2);
		driver.findElement(By.xpath("//*[@id=\"datepick_in\"]")).sendKeys("19/12/2024");
		driver.findElement(By.xpath("//*[@id=\"datepick_out\"]")).sendKeys("24/12/2024");
		WebElement c= driver.findElement(By.id("child_room"));
		Select s4=new Select(c);
		s4.selectByIndex(1);
		WebElement b= driver.findElement(By.id("adult_room"));
		Select s5=new Select(b);
		s5.selectByIndex(1);
		driver.findElement(By.xpath("//*[@id=\"Submit\"]")).click();
		Thread.sleep(7000);
		driver.findElement(By.id("radiobutton_0")).click();
		
		
		
		driver.findElement(By.xpath("//*[@id=\"continue\"]")).click();
		
		
		
		
		driver.findElement(By.xpath("//*[@id=\"first_name\"]")).sendKeys("Rakes");
	driver.findElement(By.xpath("//*[@id=\"last_name\"]")).sendKeys("h.J");
		
		
		
		driver.findElement(By.xpath("//*[@id=\"address\"]")).sendKeys("PLOTNO19LOGAMBIGAIAVENUEDASARATHANAGAREXTENSIONTADAPERUMBAKKAMPONNERI601204");
	
		driver.findElement(By.xpath("//*[@id=\"cc_num\"]")).sendKeys("1234567890123456");
		
	WebElement G= driver.findElement(By.id("cc_type"));
	Select s6=new Select(G);
		s6.selectByIndex(1);
		
	WebElement H= driver.findElement(By.id("cc_exp_month"));
		Select s7=new Select(H);
		s7.selectByIndex(1);
		
		WebElement J= driver.findElement(By.id("cc_exp_year"));
		Select s8=new Select(J);
		s8.selectByIndex(17);
		
		driver.findElement(By.xpath("//*[@id=\"cc_cvv\"]")).sendKeys("123");
		driver.findElement(By.xpath("//*[@id=\"book_now\"]")).click();
	
		 TakesScreenshot tk= (TakesScreenshot) driver;
		 File screenshotAs= tk.getScreenshotAs(OutputType.FILE);
		 System.out.println(screenshotAs);
		 File f= new File(" /Users/rakeshj/Desktop/screenshot/Screen.png");
		 FileUtils.copyFile(screenshotAs, f);
		 System.out.println("Successfully taken the Screenshot");
		
		 
		 
		
		
		
		driver.quit();
		Thread.sleep(3000);
				
		
		
	}
	
}

