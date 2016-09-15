### laios10appdevesst1
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
