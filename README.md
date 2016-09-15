### laios10appdevesst1
####2.
#####Dismiss the keyboard with delegation
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
