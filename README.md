# EasyNativeAlert

A simple swift helper that helps you easily create and use some forms of alerts.

# Usage

1- Copy AlertManager.swift file to your project target.

2- Call AlertManager singletone in your desired block and preset your custom alert.


Notice: You can customise each method directly in the AlertManager class


# Extra
Introduction to the alerts:

    1. func showAlert(parent: UIViewController, title: String, body: String, buttonTitles: [String], style: UIAlertController.Style, showCancelButton: Bool, completion: (Int?) -> ()):
    
        This is the first use case of AlertManager, just complete function arguments;
    
         title: Alert title,
         body: Alert message text, 
         buttonTitles: Array of strings that you can fill it by alert's button titles,
         style: Alert presentation style (default is .actionSheet),
         showCancelButton: Is a boolian that defines if alert should has cancel button or not (default is True).
         
         
         Usage Example:
         
            AlertManager.shared.showAlert(parent: self, title: "Dublicated item!", body: "The title you have entered is already exist", buttonTitles: ["Try again"], style: .alert, showCancelButton: true) { buttonIndex in //buttonIndex is the index you can figure which button is tapped
                if buttonIndex == 0 {
                    self.newItemButtonTapped()
                }
            }
         
    ---------------------------------------------------------------------------------------------------------------------------------------------------

    2. func showAlertWithTextField(parent: UIViewController, title: String, placeHolder: String, buttonTitle: String, style: UIAlertController.Style, showCancelButton: Bool, completion: (String?) -> ()):
    
        This is the second use case of AlertManager. This a system alert with one textField and some buttons. You should complete function arguments just like the above;
        
         title: Alert title,
         placeHolder: Alert textField placeholder text, 
         buttonTitles: Array of strings that you can fill it by alert's button titles,
         style: Alert presentation style (default is .alert),
         showCancelButton: Is a boolian that defines if alert should has cancel button or not (default is True).
         
         
         Usage Example:
         
            AlertManager.shared.showAlertWithTextField(parent: self, title: "Add new item", placeHolder: "Write an item to remember", buttonTitle: "Add", style: .alert, showCancelButton: true) {}

    ---------------------------------------------------------------------------------------------------------------------------------------------------

    3. func showCompleteFormOfAlert(parent: UIViewController, title: String, message: String, placeHolders: [String], buttonTitles: [String], style: UIAlertController.Style, showCancelButton: Bool, completion: (Int?) -> (), textCompletion: ([String]) -> ()):
    
        This is the third use case of AlertManager. This a system alert with some textFields and some buttons and you can you it for getting some information from user like a form for survey. You need to complete function arguments just like the above;
        
         title: Alert title,
         placeHolders: Array of alert textFields for placeholder texts, 
         buttonTitles: Array of strings that you can fill it by alert's button titles,
         style: Alert presentation style (default is .actionSheet),
         showCancelButton: Is a boolian that defines if alert should has cancel button or not (default is True).
         
         
         Usage Example:
         
            AlertManager.shared.showCompleteFormOfAlert(parent: self, title: "Add items", message: "", placeHolders: ["Title of purchase","Price"], buttonTitles: ["Add"], style: .alert, showCancelButton: true) { _ in
            } textCompletion: { [self] texts in
                print(texts)
            }
