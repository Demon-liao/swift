创建label


func  createLabel(w:Int,h:Int)->UILabel{
        var label = UILabel()
        label.frame=CGRect(x:0,y:0,width:w,height:h)
        println(label.frame.height)
        label.text = "foos"
        label.setTranslatesAutoresizingMaskIntoConstraints(false)
        label.textColor=UIColor(red:255, green:0, blue:0, alpha: 1);
        label.backgroundColor=UIColor(red:0.06, green:1.0, blue:0, alpha: 1);
        label.textAlignment=NSTextAlignment.Center
        return label
    }
