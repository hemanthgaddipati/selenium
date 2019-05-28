Driver:

import org.openqa.selenium.webdriver;
import org.openqa.selenium.chrome.chromedriver;
import org.openqa.selenium.firefox.firefoxdriver;
public class driversetup
{
WebDriver driver;
public static string url = "";
Thread.sleep(3000);
public WebDriver setup()
{
system.setProperty("webdriver.chrome.driver","D:\\chrome.exe");
WebDriver driver = new ChromeDriver();
driver.navigate().to(Driversetup.url);
driver.manage().window().maximize();
return driver();
}
public WebDriver setupFirefox()
{
system.setProperty("webdriver.geckodriver","D:\\geckodriver.exe");
WebDriver driver = new FirefoxDriver();
driver.navigate().to(Driversetup.url);
driver.manage().window().maximize();
return driver();
}
}

ExcelData:

import java.io.FileInputstream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.apache.poi.usermodel.XSSFcell;
import java.apache.poi.usermodel.XSSFSheet;
import java.apache.poi.usermodel.XSSFWorkbook;
public class executables 
{
Public static string getExceldata(int a, int b) throws FileNotFounfException, IOException
{
XSSFWorkbook workbook = newXSSFWorkbook(new FileInputStream("D:\\"));
XSSFSheet sheet = workbook.getsheetAt(0);
XSSFCell cell = sheet.getRow(a).getCell(b);
string value = cell.getStringCellValue();
return value;
}
}

Annotations:

Package selenium;
import org.testing.annotations.AfterTest;
import org.testing.annotations.BeforeTest;
import org.testing.annotations.Test;
public class annotations
{
@BeforeTest
public void initializeBrowser()
{
DriverManager.openBrowser();
DriverManager.openURL();
}
@Test
public void TC_01()throws Exception
{
Homepage hp = new HomePage();
hp.searchResults();
}
@AfterTest
public void tearDow()
{
DriverManager.closeBrowser();
}
}

Main:

import java.io.FileNotFoundException;
import java.io.IOException;
import java.util.concurrent.TimeUnit;
import java.util.Iterator;
import java.util.List;
import java.util.Set;
import org.openqa.selenium.By;
import org.openqa.selenium.webdriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.chromedriver;
import org.openqa.selenium.chrome.chromeoptions;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.Test;
public class search extends Driversetup
{
WebDriver driver;
@BeforeMethod
public void driver()
{
driver= setup();
driver =setupFirefox();
}
@test
public void search() throws FileNotFoundException,IOException, InterruptedException
{
................................................................
}
@AfterMethod
pulic void driverquit()
{
driver.quit();
}
}



Axis:

 package Learning;
  
 import org.openqa.selenium.By;
 import org.openqa.selenium.WebDriver;
 import org.openqa.selenium.chrome.ChromeDriver;
  
 public class AxisBank {
 
public static void main(String[] args) throws InterruptedException {
// TODO Auto-generated method stub
 
System.setProperty("webdriver.chrome.driver","D:\\chromedriver_win32\\chromedriver.exe");
WebDriver driver=new ChromeDriver();
driver.get("https://www.axisbank.com/");
driver.manage().window().maximize();
String Title=driver.getTitle();
System.out.println(Title);
Thread.sleep(2000);
//driver.switchTo().frame("nvpush_popup_background_iframe");
//driver.findElement(By.xpath("//body[@class=\"homeBody\"]//div[@id=\"nvpush_cross\"]")).click();
driver.findElement(By.id("nvpush_cross")).click();
driver.switchTo().defaultContent();
Thread.sleep(5000);
driver.findElement(By.xpath("//a[@class=\"clickDetails js-clickdetail iconLink search lnkSmartSearch\"]")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//input[@class=\"headsearch1\"]")).click();
driver.findElement(By.xpath("//input[@class=\"headsearch1\"]")).sendKeys("fd ");
Thread.sleep(2000);
driver.findElement(By.xpath("//a[@href=\"https://www.axisbank.com/personal/calculators/fd-monthly-investment-calculator\"]")).click();
Thread.sleep(5000);
driver.findElement(By.xpath("//div[@class=\"input-group\"]//input[@name=\"ctl00$Body$C002$txtAmount\"]")).clear();
driver.findElement(By.xpath("//div[@class=\"input-group\"]//input[@name=\"ctl00$Body$C002$txtAmount\"]")).sendKeys("50000");
//Thread.sleep(6000);
driver.findElement(By.xpath("//a[@id=\"ctl00_Body_C002_btnCal\"]")).click();
int oops=driver.findElements(By.xpath("//p[contains(text(),'Something went wrong. Please visit after sometime.')]")).size();
if(oops==1){
driver.navigate().back();
Thread.sleep(6000);
String name=driver.findElement(By.xpath("//div[@class=\"piechart_container\"]//span[@class=\"maturity_text\"]")).getText();
System.out.println(name);
Thread.sleep(2000);
String Amount=driver.findElement(By.xpath("//div[@class=\"piechart_container\"]//span[@class=\"maturity_amt grossTotal\"]")).getText();
System.out.println(Amount);
driver.close();
}
 
else{
String name=driver.findElement(By.xpath("//div[@class=\"piechart_container\"]//span[@class=\"maturity_text\"]")).getText();
System.out.println(name);
Thread.sleep(2000);
String Amount=driver.findElement(By.xpath("//div[@class=\"piechart_container\"]//span[@class=\"maturity_amt grossTotal\"]")).getText();
System.out.println(Amount);
driver.close();
}
}
 
}

GOibibo:
        import org.openqa.selenium.By;
        import org.openqa.selenium.Keys;
        import org.openqa.selenium.WebDriver;
        import org.openqa.selenium.chrome.ChromeDriver;
         
        public class IBIBO 
        {
         
        public static void main(String[] args) throws InterruptedException 
        {
        System.setProperty("webdriver.chrome.driver","C:\\Program Files (x86)\\SeleniumJava\\chromedriver.exe");
        WebDriver driver= new ChromeDriver();
         
        driver.get("https://www.goibibo.com/"); 
        driver.manage().window().maximize();
        Thread.sleep(2000);
         
        driver.findElement(By.xpath("//input[@id='gi_roundtrip_label']")).click();
         
        driver.findElement(By.xpath("//input[@id='gosuggest_inputSrc']")).click();
        driver.findElement(By.xpath("//input[@id='gosuggest_inputSrc']")).sendKeys("CHENNAI");
        Thread.sleep(1000);
        driver.findElement(By.xpath("//input[@id='gosuggest_inputSrc']")).sendKeys(Keys.chord(Keys.ARROW_DOWN, Keys.ENTER));
         
        driver.findElement(By.xpath("//input[@id='gosuggest_inputDest']")).click();
        driver.findElement(By.xpath("//input[@id='gosuggest_inputDest']")).sendKeys("LONDON");
        Thread.sleep(1000);
        driver.findElement(By.xpath("//input[@id='gosuggest_inputDest']")).sendKeys(Keys.chord(Keys.ARROW_DOWN, Keys.ENTER));
         
        driver.findElement(By.xpath("//div[@id='fare_20190120']")).click();
        driver.findElement(By.xpath("//div[@id='fare_20190221']")).click();
         
        driver.findElement(By.xpath("//span[@class='ico15 grey padT5 padL10 fl']")).click();
        driver.findElement(By.xpath("//button[@class='fl plusSpin']")).click();
        driver.findElement(By.xpath("//a[@class='icon-cancel-circle fr marginT10 marginR10 fr greyDr mobdn']")).click();
         
        driver.findElement(By.xpath("//select[@class='form-control selectLarge width100']")).click();
        driver.findElement(By.xpath("//select[@class='form-control selectLarge width100']")).sendKeys("ECONOMY");
        Thread.sleep(1000);
        driver.findElement(By.xpath("//select[@class='form-control selectLarge width100']")).sendKeys(Keys.ENTER);
         
        driver.findElement(By.xpath("//button[@id='gi_search_btn']")).click();
        Thread.sleep(3000);
         
        String A= driver.findElement(By.xpath("(//span[@class='fb'])[1]")).getText();
        System.out.println("Departure Time from Chennai is " +A);
         
        String B= driver.findElement(By.xpath("(//span[@class='fb'])[4]")).getText();
        System.out.println("Arrival Return Time at Chennai is " +B);
         
        driver.findElement(By.xpath("(//input[@class='button orange fr '])[1]")).click();
        Thread.sleep(2000);
         
        driver.findElement(By.xpath("(//a[text()='Baggage and Fare Rules'])[1]")).click();
        Thread.sleep(1000);
        driver.findElement(By.xpath("//a[@id='fltFareRulesTab']")).click();
        Thread.sleep(2000);
         
        driver.close();
        }
        }


MakeMyTrip:
        import org.openqa.selenium.By;
        import org.openqa.selenium.Keys;
        import org.openqa.selenium.WebDriver;
        import org.openqa.selenium.chrome.ChromeDriver;
         
        public class Trips 
        {
        public static void main(String[] args) throws InterruptedException 
        {
        System.setProperty("webdriver.chrome.driver", "C:\\\\Program Files (x86)\\\\SeleniumJava\\\\chromedriver.exe");
        WebDriver driver = new ChromeDriver();
         
        driver.manage().window().maximize();
         
        driver.get("https://www.makemytrip.com/");
        Thread.sleep(9000);
         
        driver.findElement(By.xpath("//label[@for='switch__input_2']")).click();
        Thread.sleep(5000);
        
        driver.findElement(By.xpath("//input[@id='hp-widget__sfrom']")).click();
        driver.findElement(By.xpath("//input[@id='hp-widget__sfrom']")).sendKeys("CHENNAI");
        Thread.sleep(2000);
         
        driver.findElement(By.xpath("//input[@id='hp-widget__sfrom']")).sendKeys(Keys.ENTER);
        Thread.sleep(2000);
         
        driver.findElement(By.xpath("//input[@id='hp-widget__sTo']")).click();
        Thread.sleep(2000);
        driver.findElement(By.xpath("//input[@id='hp-widget__sTo']")).sendKeys("MUMBAI");
        Thread.sleep(2000);
        driver.findElement(By.xpath("//input[@id='hp-widget__sTo']")).sendKeys(Keys.ENTER);
       Thread.sleep(2000);
        
        driver.findElement(By.xpath("(//a[text()='14'])[1]")).click();
        
        driver.findElement(By.xpath("//input[@id='hp-widget__return']")).click();
        driver.findElement(By.xpath("(//a[text()='16'])[3]")).click();
         
        driver.findElement(By.xpath("//input[@value='1 | Economy']")).click();
        Thread.sleep(2000);
         
        driver.findElement(By.xpath("//*[@id=\"js-adult_counter\"]/li[2]")).click();
        driver.findElement(By.xpath("//*[@id=\"js-child_counter\"]/li[2]")).click();
        driver.findElement(By.xpath("//span[@id='economy']")).click();
        Thread.sleep(2000);
         
        driver.findElement(By.xpath("//button[@id='searchBtn']")).click();
        Thread.sleep(5000);
         
        driver.findElement(By.xpath("(//span[@class='radio_icon'])[2]")).click();
        Thread.sleep(2000);
         
        driver.findElement(By.xpath("//a[@class='btn btn-lg pull-right btn-primary-red']")).click();
        Thread.sleep(2000);
         
        String A= driver.findElement(By.xpath("(//span[@class='pull-left col-lg-5 col-md-5 col-sm-4 col-xs-4 text-right review_red ng-binding'])[2]")).getText();
        System.out.println("Total Fare is " +A);
         
        driver.close();
         
         
        }
         
        }
        

ClearTrip:
        driver.findElement(By.xpath("//input[@id='RoundTrip']")).click();
         
        driver.findElement(By.xpath("//input[@id='FromTag']")).click();
        driver.findElement(By.xpath("//input[@id='FromTag']")).sendKeys("CHENNAI");
        Thread.sleep(5000);
        driver.findElement(By.xpath("//input[@id='FromTag']")).sendKeys(Keys.ENTER);
         
        driver.findElement(By.xpath("//input[@id='ToTag']")).sendKeys("MUNICH");
        Thread.sleep(5000);
        driver.findElement(By.xpath("//input[@id='FromTag']")).sendKeys(Keys.chord(Keys.ARROW_DOWN, Keys.ENTER));
         
        driver.findElement(By.xpath("//input[@title='Depart date']")).click();
        driver.findElement(By.xpath("(//a[text()='15'])[2]")).click();
        Thread.sleep(2000);
         
        driver.findElement(By.xpath("//input[@title='Return date']")).click();
       driver.findElement(By.xpath("(//a[text()='18'])[2]")).click();
        Thread.sleep(2000);
         
        driver.findElement(By.xpath("//select[@id='Adults']")).click();
        driver.findElement(By.xpath("//select[@id='Adults']")).sendKeys("3", Keys.chord(Keys.ENTER));
        Thread.sleep(2000);
         
        driver.findElement(By.xpath("//input[@id='SearchBtn']")).click();
        Thread.sleep(15000);
         
        driver.findElement(By.xpath("(//button[@class='booking'])[1]")).click();
        Thread.sleep(8000);
         
        driver.findElement(By.xpath("//a[text()='more info']")).click();
         
        driver.switchTo().frame("modal_window");
        String A= driver.findElement(By.xpath("//p[@rel='bTooltip'])[2]")).getText();
        System.out.println("Baggage Allowance is " +A);
         
        driver.close();
         
        }
         
        }
        
        
Savaari: 


// Savaari

System.setProperty("webdriver.chrome.driver","");
WebDriver driver=new ChromeDriver();
driver.manage().window().maximize();

try{

driver.get("https://www.savaari.com/");
Thread.sleep(2000);
driver.findElement(By.xpath("//label[@for='oneway_radio']")).click();
Thread.sleep(2000);

driver.findElement(By.xpath("//input[@id='fromCityList']")).click();
//driver.findElement(By.xpath("//input[@id='fromCityList']")).clear();
driver.findElement(By.xpath("//input[@id='fromCityList']).sendKeys("Mumbai");
Thread.sleep(2000);

Robot dropdown=null;
dropdown=new Robot();
dropdown.keyPress(KeyEvent.VK_DOWN);
dropdown.keyRelease(KeyEvent.VK_DOWN);
dropdown.keyPress(KeyEvent.VK_ENTER);
dropdown.keyRelease(KeyEvent.VK_ENTER);

driver.findElement(By.xpath("//input[@placeholder='Start typing city - e.g. Mysore']")).click();
//driver.findElement(By.xpath("//input[@placeholder='Start typing city - e.g. Mysore']")).clear();
driver.findElement(By.xpath("//input[@placeholder='Start typing city - e.g. Mysore']")).sendKeys("Pune");
Thread.sleep(2000);

dropdown.keyPress(KeyEvent.VK_DOWN);
dropdown.keyRelease(KeyEvent.VK_DOWN);
dropdown.keyPress(KeyEvent.VK_ENTER);
dropdown.keyRelease(KeyEvent.VK_ENTER);

driver.findElement(By.xpath("//input[@class='ng-tns-c11-7 form-control ui-inputtext ui-widget ui-state-default ui-corner-all']")).click();
//driver.findElement(By.xpath("//input[@class='ng-tns-c11-7 form-control ui-inputtext ui-widget ui-state-default ui-corner-all']")).clear();
driver.findElement(By.xpath("(//span[@class='fa fa-angle-right']")).click();
driver.findElement(By.xpath("((//a[@class='ui-state-default ng-tns-c11-7'])[13]")).click();
Thread.sleep(1000);

driver.findElement(By.xpath("//select[@id='pickUpTime']")).click();
//driver.findElement(By.xpath("//select[@id='pickUpTime']")).clear();
//driver.findElement(By.xpath("(//select[@id='pickUpTime']")).sendkeys();
Thread.sleep(1000);

dropdown.keyPress(KeyEvent.VK_DOWN);
dropdown.keyRelease(KeyEvent.VK_DOWN);
dropdown.keyPress(KeyEvent.VK_ENTER);
dropdown.keyRelease(KeyEvent.VK_ENTER);


driver.findElement(By.xpath("//button[@class='book-button btn']")).click();
Thread.sleep(2000);

String carname=driver.findElement(By.xpath("(//div[@class='carNamesDesktop'])[1]")).getText();
System.out.println(carname);

driver.findElement(By.xpath("(//img[@alt='Savaari'])[1]")).click();
Thread.sleep(2000);

}//try
catch(Exception e){
e.printStackTrace();
}//catch

Thread.sleep(1000);
driver.quit();



