### laios10appdevesst1
####2.
#####First responders
cmd+k toggle keyboard(in simulator)
```
become/resignFirstResponder()
```
touch View to end editing:
```
override func touchesBegan(_ touches:Set<UITouch>, with event:UIEvent?){
  
}
```
#####Dismiss the keyboard with delegation
```
class ViewController: UIViewController, UITextFieldDelegate
```
The ViewController can be a delegate for a UITextField,  
the next step is to assign this ViewController class as a delegate of the textfield.  
Method 1:
```
override func viewDidLoad(){
  super.viewDidLoad()
  myTextField.delegate = self
}
```
Method 2: storyboard  
go to storyboard->click the textfield in rightside(connections inspector), click delegate,drag to controller (1 of 3)  

textFieldShouldReturn //handle return key
```
func textFieldShouldReturn(_ textField: UITextField)->Bool{
  myTextField.resignFirstResponder()
  return false  //back to screen.
  //return true for normal behavior
}
```
customize keyboard.  
select textfield->sidebar (4 of 6) set return key=done

#####Troubleshoot UI-to-code connections
If you see some event handler's circie is not filled, go to storyboard, click the element that is not handles (say, a button.) click the button in storyboard, choose Send events->touch up inside, drag to controller icon (1 of 3)
####3. Build a Simple App
#####Code your app
memorize the difference between android.
```
@IBOutlet weak var textInput: UITextField!
@IBOutlet weal var textOutput: UITextView!
var items:[String]=[]
@IBAction func addItem(_ sender:AnyObject){
  if(textInput.text! ==""){return}
  items.append(textInput.text); //in android it should be toString()
  textOutput.text=""
  for item in items{
    textOutput.text.append("\(item)\n")
  }
  textInput.text=""
  textInput.resignFirstResponder()
}
```
