### 自定义控件

smallwidget.cpp

~~~c++
#include "smallwidget.h"
#include<QSpinBox>
#include<QSlider>
#include<QHBoxLayout>
smallwidget::smallwidget(QWidget *parent) : QWidget(parent)
{
 QSpinBox *spin=new QSpinBox(this);
 QSlider *slider=new QSlider(Qt::Horizontal,this);
 QHBoxLayout  *hlayout=new QHBoxLayout(this);
 hlayout->addWidget(spin);
hlayout->addWidget(slider);
//setLayout(hlayout);
connect (spin ,static_cast<void (QSpinBox::*)(int)>(&QSpinBox::valueChanged),
         slider,    &QSlider::setValue);
connect(slider,&QSlider::valueChanged,spin,&QSpinBox::setValue);
}

~~~

### QT样式表

![image-20201126112945652](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20201126112945652.png)

![image-20201126113237965](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20201126113237965.png)