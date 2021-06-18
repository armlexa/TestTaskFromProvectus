# TestTaskFromProvectus
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.ExpectedCondition;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.Select;
import org.openqa.selenium.support.ui.WebDriverWait;
import java.time.Duration;

public class Main {
    public static void main(String[] args) {

        System.setProperty("webdriver.chrome.driver", "C:\\Java\\Chromedriver\\chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(5));
        driver.get("https://demoqa.com");

        WebElement Forms = (new WebDriverWait(driver, Duration.ofSeconds(5))
                .until(ExpectedConditions.presenceOfElementLocated(By.xpath("(//div[@class=\'card mt-4 top-card\'])[2]"))));
        Forms.click();

        WebElement PractiseForm = (new WebDriverWait(driver, Duration.ofSeconds(5))
                .until(ExpectedConditions.presenceOfElementLocated(By.xpath("//*[@class=\'element-list collapse show\']"))));
        PractiseForm.click();

        WebElement Name = driver.findElement(By.xpath(("(//*[@class=' mr-sm-2 form-control'])[1]")));
        Name.sendKeys("Oleksii");

        WebElement LastName = driver.findElement(By.xpath(("(//*[@class=' mr-sm-2 form-control'])[2]")));
        LastName.sendKeys("Haievoi");

        WebElement Email = driver.findElement(By.xpath(("//*[@class=\'mr-sm-2 form-control\']")));
        Email.sendKeys("armlexa92@gmail.com");

        WebElement Mail = driver.findElement(By.xpath(("(//*[@class='custom-control-label'])[1]")));
        Mail.click();

        WebElement Mobile = driver.findElement(By.xpath(("(//*[@class=' mr-sm-2 form-control'])[3]")));
        Mobile.sendKeys("1234567890");

        WebElement DateOfBirth = driver.findElement(By.xpath(("(//*[@class=\'form-control\'])[1]")));
        DateOfBirth.clear();
        DateOfBirth.sendKeys("17 Feb 1992");
        Actions action = new Actions(driver);
        action.sendKeys(Keys.ESCAPE).build().perform();

        WebElement Sports = driver.findElement(By.xpath(("(//*[@class=\'custom-control-label\'])[4]")));
        Sports.click();

        WebElement Reading = driver.findElement(By.xpath(("(//*[@class=\'custom-control-label\'])[5]")));
        Reading.click();

        WebElement Music = driver.findElement(By.xpath(("(//*[@class=\'custom-control-label\'])[6]")));
        Music.click();

        WebElement CurrentAddress = driver.findElement(By.xpath(("(//*[@class=\'form-control\'])[2]")));
        CurrentAddress.sendKeys("Current Address");

        WebElement Submit = driver.findElement(By.xpath(("//button[@class=\'btn btn-primary\']")));
        Submit.sendKeys(Keys.DOWN);
        Submit.click();
    }
}
