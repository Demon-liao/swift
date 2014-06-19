###创建label

<pre code="swift">
func  createLabel(w:Int,h:Int)->UILabel{
        var label = UILabel()
        label.frame=CGRect(x:0,y:0,width:w,height:h)
        println(label.frame.height)
        label.text = "foos"
        label.setTranslatesAutoresizingMaskIntoConstraints(false) //改为false 对UI进行约束设置 默认值是true
        label.textColor=UIColor(red:255, green:0, blue:0, alpha: 1);
        label.backgroundColor=UIColor(red:0.06, green:1.0, blue:0, alpha: 1);
        label.textAlignment=NSTextAlignment.Center
        return label
    }
</pre>

###设置UIview约束的条件方法


<pre code="swift">
###先把UI加入到窗口，否则会报错
    var labels=["label":label]
    self.view.addSubview(label) 
###对UI的高度重新设置
     self.view.addConstraints(NSLayoutConstraint.constraintsWithVisualFormat("[label(125)]", options:NSLayoutFormatOptions(0), metrics:nil, views:labels))
         self.view.addConstraints(NSLayoutConstraint.constraintsWithVisualFormat("V:[label(125)]", options:NSLayoutFormatOptions(0), metrics:nil, views:labels)
###设置底部对齐，距离底部20， 如果需要bottom-right 对齐方式，重新再写一条靠右对齐即可            
     self.view.addConstraint(NSLayoutConstraint(item: label, attribute:NSLayoutAttribute.Bottom ,relatedBy:NSLayoutRelation.Equal, toItem:self.view ,attribute:NSLayoutAttribute.Bottom, multiplier:1.0, constant:-20.0))
</pre>
