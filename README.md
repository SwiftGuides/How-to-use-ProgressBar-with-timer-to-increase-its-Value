# How-to-use-ProgressBar-with-timer-to-increase-its-Value
Use ProgressBar with timer to increase value at specific time


Soucre :- https://stackoverflow.com/a/51314018/10422074


```
import UIKit

class ViewController: UIViewController {

@IBOutlet var progessV : UIProgressView!
var progressValue : Float = 0
var timer : Timer?

override func viewDidLoad() {
    super.viewDidLoad()
    timer = Timer.scheduledTimer(timeInterval: 1, target: self, selector: #selector(update), userInfo: nil, repeats: true)
}

@objc func update(){
    if (progressValue < 1)
    {
        progressValue += 0.1
        progessV.progress = progressValue
    }
    else
    {
        timer?.invalidate()
        timer = nil
    }
}
@IBAction func reset() {
    progressValue = 0
}
}
