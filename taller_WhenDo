package basicAppium;
import io.appium.java_client.AppiumDriver;
import io.appium.java_client.android.AndroidDriver;
import org.junit.After;
import org.junit.Assert;
import org.junit.Before;
import org.junit.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.remote.DesiredCapabilities;
import java.net.MalformedURLException;
import java.net.URL;
import java.util.concurrent.TimeUnit;

public class taller_WhenDo {
    private AppiumDriver driver;

    @Before
    public void beforeTest() throws MalformedURLException {
        // configuracion para la conexion
        DesiredCapabilities capabilities= new DesiredCapabilities();
        capabilities.setCapability("deviceName","moto g(6) play");
        capabilities.setCapability("platformVersion","8.0.0");
        capabilities.setCapability("appPackage","com.vrproductiveapps.whendo");
        capabilities.setCapability("appActivity",".ui.HomeActivity");
        capabilities.setCapability("platformName","Android");

        // driver apunte a nuestro appiumDesktop
        driver= new AndroidDriver(new URL("http://127.0.0.1:4723/wd/hub"),capabilities);

        // implicit:un tiempo de espera para todos los componentes de UI. el explicit sobreescribe al implicit
        driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
    }

    @Test
    public void verify_Task_isAdded(){
        String title ="Title Auto1";
        String notes="This is my note1";

        //add task
        driver.findElement(By.id("com.vrproductiveapps.whendo:id/fab")).click();
        //add reminder
        driver.findElement(By.id("com.vrproductiveapps.whendo:id/note_item_reminder")).click();
        //add date
        driver.findElement(By.id("com.vrproductiveapps.whendo:id/due_date")).click();
        driver.findElement(By.id("android:id/button3")).click();
        driver.findElement(By.id("android:id/button1")).click();
        //add time
        driver.findElement(By.id("com.vrproductiveapps.whendo:id/time")).click();
        //driver.findElement(By.xpath("//android.widget.RadialTimePickerView.RadialPickerTouchHelper[@content-desc='6']"));
        driver.findElement(By.id("android:id/button1")).click();
        //add reminder
        driver.findElement(By.id("com.vrproductiveapps.whendo:id/reminder")).click();
        driver.findElement(By.xpath("//android.widget.RadioButton[3]")).click();
        //add repeat
        driver.findElement(By.id("com.vrproductiveapps.whendo:id/repeat")).click();
        driver.findElement(By.xpath("//android.widget.RadioButton[3]")).click();
        //add title
        driver.findElement(By.id("com.vrproductiveapps.whendo:id/noteTextTitle")).sendKeys(title);
        //add Note
        driver.findElement(By.id("com.vrproductiveapps.whendo:id/noteTextNotes")).sendKeys(notes);
        //Save
        driver.findElement(By.id("com.vrproductiveapps.whendo:id/saveItem")).click();
        //verify task title and note is displayed listed
        boolean isDisplayedTitle=driver.findElement(By.xpath("//android.widget.TextView[@text='"+title+"']")).isDisplayed();
        Assert.assertTrue("ERROR el titulo no es mostrado en la lista",isDisplayedTitle);

        boolean isDisplayedNote=driver.findElement(By.xpath("//android.widget.TextView[@text='"+notes+"']")).isDisplayed();
        Assert.assertTrue("ERROR la nota no es mostrado en la lista",isDisplayedNote);


    }

    @After
    public void afterTest(){
        driver.quit();
    }

}
