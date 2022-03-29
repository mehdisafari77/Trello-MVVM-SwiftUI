# Trello-MVVM-SwiftUI
A simple drag and drop Trello like task manager in SwiftUI

## Summary
This is a crypto tracking app using the CoinGecko to get data about coins, and users are able to add coins to their portfolio to keep track of them. Data is saved using CoreData and everything is coded in SwiftUI. (THE APP STILL HAS SIGNUP/SIGNIN YET TO BE IMPLEMENTED)

## Built With
* [SwiftUI](https://developer.apple.com/tutorials/swiftui)
* [UIKit](https://developer.apple.com/documentation/uikit)

## Gif of App
![Gif](./Trello-MVVM-SwiftUI/Assets.xcassets/gif.dataset/gif.gif)

## Installation Steps For Local Running
1. Clone project.
2. Open terminal
3. cd 'your-desired-path'
4. git clone 'paste-link-here'
5. open project in Xcode and run

## Code Snippet Of Getting Alert Making Edits
```swift
func presentAlertTextField(title: String, message: String? = nil, defaultTextFieldText: String? = nil, confirmAction: @escaping (String?) -> ()) {
        guard let rootVC = (UIApplication.shared.connectedScenes.first as? UIWindowScene)?
                .keyWindow?
                .rootViewController else { return }
        
        let alertController = UIAlertController(title: title, message: message, preferredStyle: .alert)
        alertController.addTextField { textField in
            textField.text = defaultTextFieldText
        }
        alertController.addAction(.init(title: "Cancel", style: .cancel) { _ in })
        alertController.addAction(.init(title: "Save", style: .default, handler: { _ in
            guard let textField = alertController.textFields?.first else { return }
            confirmAction(textField.text)
        }))
        rootVC.present(alertController, animated: true, completion: nil)
    }
```


## Author

* **Mehdi Safari**

- [Link to Github](https://github.com/mehdisafari77)
- [Link to LinkedIn](https://www.linkedin.com/in/mehdi-safari-992799142/)
