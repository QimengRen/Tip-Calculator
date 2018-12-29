# Tip-Calculator
//
//  ViewController.swift
//  Tippy-4
//
//  Created by Qimeng on 12/28/18.
//  Copyright © 2018 Ren Qimeng. All rights reserved.
//

import UIKit

class ViewController: UIViewController {
   
    @IBOutlet weak var billField: UITextField!
    @IBOutlet weak var tipLabel: UILabel!
    @IBOutlet weak var totalLabel: UILabel!
    
    @IBOutlet weak var tipControl: UISegmentedControl!
    
    
    
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
    }

    @IBAction func onTap(_ sender: Any) {
   view .endEditing(true)
    }
   
    
    @IBAction func calculateTip(_ sender: Any) {
        
        
        let tipPercentages = [0.18,0.2,0.25]
        let Bill = Double(billField.text!) ?? 0
        let Tip = Bill * tipPercentages[tipControl.selectedSegmentIndex]
        let Total = Bill + Tip
        
        tipLabel.text = String(format: "$%.2f", Tip)
        totalLabel.text = String(format: "$%.2f", Total)
        
        
        
    }
    
}
