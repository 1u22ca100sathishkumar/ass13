# ass13
1. Difference between driver.get() and driver.navigate()
Feature	driver.get()	driver.navigate()
Purpose	Opens a URL	Provides browser navigation
Methods	Only get(url)	to(), back(), forward(), refresh()
Simplicity	Simple and commonly used	More control over navigation
Usage	Initial page load	Browser history operations
Example
driver.get("https://example.com");
driver.navigate().to("https://example.com");
driver.navigate().back();
driver.navigate().forward();
driver.navigate().refresh();


📌 Note: get() internally uses navigate().to() but navigate() gives extra features.

2. Program to display result as PASS or FAIL based on title
Selenium Java Program
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class TitleValidation {

    public static void main(String[] args) {

        System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
        WebDriver driver = new ChromeDriver();

        driver.get("https://www.saucedemo.com/");

        String expectedTitle = "Swag Labs";
        String actualTitle = driver.getTitle();

        if (actualTitle.equals(expectedTitle)) {
            System.out.println("TEST CASE PASS");
        } else {
            System.out.println("TEST CASE FAIL");
        }

        driver.quit();
    }
}

3. Program to display a site in iPhone 6 screen size
Selenium Java Program (Chrome Mobile Emulation)
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;
import java.util.HashMap;
import java.util.Map;

public class IPhone6View {

    public static void main(String[] args) {

        System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");

        ChromeOptions options = new ChromeOptions();

        Map<String, String> mobileEmulation = new HashMap<>();
        mobileEmulation.put("deviceName", "iPhone 6");

        options.setExperimentalOption("mobileEmulation", mobileEmulation);

        WebDriver driver = new ChromeDriver(options);

        driver.get("https://www.saucedemo.com/");

        System.out.println("Site displayed in iPhone 6 view");

        driver.quit();
    }
}

📱 iPhone 6 Screen Size

Width: 375px

Height: 667px
