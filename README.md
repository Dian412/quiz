# quiz

package testing;

import javafx.application.Application;
import javafx.geometry.Insets;
import javafx.geometry.Pos;
import javafx.scene.Scene;
import javafx.scene.control.Label;
import javafx.scene.control.TextField;
import javafx.scene.layout.GridPane;
import javafx.stage.Stage;
import java.util.Scanner;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.control.Button;
import javafx.scene.input.ClipboardContent;
import javafx.scene.input.Clipboard;
import javafx.scene.paint.Color;
import javafx.scene.text.Text;

/** * * @author dian */

public class Testing extends Application 
{        
@Override    
public void start(Stage primaryStage) {       
GridPane grid = new GridPane();      
grid.setAlignment(Pos.CENTER);       
grid.setHgap(5);       
grid.setVgap(5);       
grid.setPadding(new Insets(10,10,10,10));   
Scene scene = new Scene(grid, 500, 200);            
final Clipboard clipboard = Clipboard.getSystemClipboard();    
final ClipboardContent content = new ClipboardContent();         
Scanner scan = new Scanner(System.in);     

Label question = new Label();     
question.setText("What is 1 + 1?");       
final TextField answer = new TextField();     
answer.setPromptText("Enter your answer");      
answer.setPrefColumnCount(10);    
String answer1 = answer.getText();   
GridPane.setConstraints(answer, 1, 1);   
grid.getChildren().add(answer);   
final Text actiontarget1 = new Text();   
final Text actiontarget2 = new Text();   
Button btn1 = new Button();    
btn1.setText("Submit");    
btn1.setOnAction((ActionEvent event) ->{ 
actiontarget1.setText("Thak you for submitting your answer.");     
actiontarget1.setFill(Color.BLACK);       });  
Button btn2 = new Button();   
btn2.setText("Cheat"); 
btn2.setOnAction((ActionEvent event) ->{   
actiontarget1.setText("You sure you want to use cheat? \nYou won't be able to get points if you use cheats.");    
actiontarget1.setFill(Color.FIREBRICK);       
});   
Button btn3 = new Button();     
btn3.setText("Skip");   
btn3.setOnAction((ActionEvent event) ->{     
actiontarget1.setText("You sure you want to skip?\nYou wont be able to get points if you skip.");     
actiontarget1.setFill(Color.FIREBRICK);    
});   
grid.add(question,0,0,4,1);   
grid.add(answer,1,1);  
grid.add(btn1,1,3);    
grid.add(btn2,2,3);   
grid.add(btn3,3,3);    
grid.add(actiontarget1,1,4);    
grid.add(actiontarget2,2,5);    
grid.setGridLinesVisible(false);   
scene.getStylesheets().add(Testing.class.getResource("testing.css").toExternalForm());       
primaryStage.setTitle("Quiz 1");   
primaryStage.setScene(scene);      
primaryStage.show();     
}    




/**     * @param args the command line arguments     */  

public static void main(String[] args) {        launch(args);    
}}
