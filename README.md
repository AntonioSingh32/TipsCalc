#Pre-work - TipsCalculator

# TipsCalculator
Tip Calculator Application for Code Path Pre Work

//
//  ViewController.swift
//  TipCalculator
//
//  Created by Clark Kent on 12/27/15.
//  Copyright © 2015 Antonio Singh. All rights reserved.
//

import UIKit

class ViewController: UIViewController {

    @IBOutlet weak var billField: UITextField!
    @IBOutlet weak var tipLabel: UILabel!
    @IBOutlet weak var totalLabel: UILabel!
    @IBOutlet weak var tipField: UITextField!
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
        tipLabel.text = "$0.00"
        totalLabel.text = "$0.00"
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }

    @IBAction func onEditingChanged(sender: AnyObject) {
    
    let billAmount = NSString (string: billField.text!).doubleValue
    let percent = NSString (string: tipField.text!).doubleValue
    let tip = billAmount * percent/100
    let total = billAmount + tip
    
        
    tipLabel.text = "$\(tip)"
    totalLabel.text = "$\(total)"
        
    tipLabel.text = String (format: "$%.2f", tip)
    totalLabel.text = String (format: "$%.2f", total)
        
    }

    @IBAction func onTap(sender: AnyObject) {
    view.endEditing(true)

    }
}

**Tips Calculator ** is a tip calculator application for iOS.

Submitted by: Antonio Singh

Time spent: 7 hours spent in total

#User Stories

* [ ] User can enter a bill amount, choose a tip percentage, and see the tip and total values.

## Video Walkthrough

<img src='https://fat.gfycat.com/YellowishHandyAmericanavocet.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />

## Notes

Only complications were during the function onTap because it repeatedly gave me the error "Editor placeholder in source code" whenever I added the bool view.endEditing. I finally fixed it by removing the force bool in parentheses and putting the value true in its place.

Rather than going with the preset percentages in the basic version of the calculator I wanted to give the users the ability to make their own percentages if need be or if they had their own preset tip percentages in mind.


## License

    Copyright [2015] [Antonio Singh]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
