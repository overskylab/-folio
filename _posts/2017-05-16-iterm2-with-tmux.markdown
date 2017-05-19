---
layout: post
title:  My working tools (iTerm2 + TMUX + Storm)
date: 2017-05-19 00:00:00
description: This's about iTerm2 program on MacOS work together with TMUX software
---
Hi friends,

เนื่องจากช่วงนี้ได้ทำงานที่ต้องใช้ SSH เยอะมาก อย่างที่รู้ๆกันเราจำเป็นต้องมีโปรแกรมที่ช่วยในการทำงาน ตัวอย่างโปรแกรมพื้นฐานเช่น Terminal บนแมค และ Linux หรือจะเป็น โปรแกรมที่นิยมมากใน Windows นั่นคือ Putty

พอถึงจุดนึง ที่จำเป็นจำต้องใช้งานมากขึ้น เราก็จะมองหาเครื่องมือที่ทำให้เราสะดวกสบายมากขึ้น อย่างเช่น SecureCRT บนวินโดว์ แล้วคำถามคือบน MacOS ล่ะ...

ที่จริงโปรแกรม SecureCRT ทำมาเพื่อรองรับการใช้งานบน MacOS แต่ว่ามันไม่สวย (คหสต.ล้วนๆ)

เข้าเรื่องกันเถอะ ฮ่าๆๆ
เราจะมาพูดถึงสิ่งที่ใช้ทดแทนหรือหลีกเลี่ยงการใช้ SecureCRT บนแมคตอนนี้ ซึ่งแน่นอนว่าการพยายามต้องยุ่งยากกว่าการติดตั้งโปรแกรมๆเดียวซึ่งนั่นคือ....

การใช้โปรแกรม iTerm2 ร่วมกับการใช้ TMUX มาดูสิ่งโจทย์ในตอนนี้กัน
1. สามารถปิดโปรแกรมได้ทันที และ restore history ได้เมื่อเปิดโปรแกรมขึ้นมาใหม่ เพื่อที่จะสามารถทำงานต่อได้ทันที
2. สามารถส่ง command ไปยัง tabs ที่เปิดอยู่ได้ทั้งหมด โดยพิมพ์แค่ครั้งเดียว
3. สามารถ SSH เข้าถึง Servers ได้หลายเครื่องพร้อมๆกัน (จัด group) เหมือน SecureCRT [ยังทำไม่ได้] แต่ใช้ต้องจัดการ SSH แทนไปก่อนนั่นคือ Storm
<div class="img_row">
	<img class="col three" src="{{ site.baseurl }}/img/1.png">
</div>
<div class="col three caption">
	 ตัวอย่างโปรแกรม iTerm2 ที่ใช้งานร่วมกับ TMUX
</div>


ขั้นตอน
1. {% highlight bash %}brew install tmux{% endhighlight %}
2. {% highlight bash %}tmux -CC{% endhighlight %} เพื่อเริ่มสร้าง Session
3. ใช้งาน/ควบคุม iTerm2
{% highlight bash %}
cmd + t: เปิด tab ใหม่ สามารถเลือกได้ว่าเป็น tmux หรือ bash ธรรมดา
cmd + n: เปิดหน้าต่างใหม่
cmd + d: แบ่งหน้าต่าง Session ในแนวนอน
cmd + shift + d: แบ่งหน้าต่าง Session ในแนวตั้ง
{% endhighlight %}
4. ปิด tab หรือหน้าต่างจะมีให้เลือก Hide เพื่อเก็บไว้กลับมาใช้งานใหม่ หรือ Kill เพื่อปิดการทำงานของหน้านั้น
5. เมื่อกลับมาใช้งานใหม่ให้ใช้คำสั่ง {% highlight bash %}tmux -CC attach{% endhighlight %}


Tips
- Cmd + ctrl + shift + enter : tmux session management
- Cmd + Shift + i : Send command to all panes & all sessions (tabs)
- Cmd + option + i : Send command to all panes in a session (tab)
