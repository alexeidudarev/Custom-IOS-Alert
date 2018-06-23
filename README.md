# Custom-IOS-Alert
Making customisation for build-in Apple alert 

Getting Started

Go to your Project Inspector’s General tab and scroll down to where it says, “Embedded Binaries.” Click the + button and then Add Other. A Finder window will drop down, and here you need to select the ADModalStatus.xcodeproj framework that we created earlier. You’ll notice that our Framework was added to the Project Navigator!
And then add framework to Embedded Binaries.

//framework implementation 
import UIKit

//dont forget to import framework to this class
import ADModalStatus

class ViewController: UIViewController {
  
    //custom outlet for save button
    @IBAction func saveTapped(_ sender: Any) {
        presentModalStatusView()
    }
    func presentModalStatusView() {    
        let modalView = ADModalStatusView(frame: self.view.bounds)
        let downloadImage = UIImage(named: "cloud") ?? UIImage()
        
        //add some png image to your project accets first
        modalView.set(image: downloadImage)
        
        modalView.set(headline: "Downloading")
        modalView.set(subheading: "image from web")
        view.addSubview(modalView)
    }
}

