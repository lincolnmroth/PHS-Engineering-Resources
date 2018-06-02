##### Power System:

Your robot needs power somehow, so you need a power system.

###### Batteries, lipo, nimh, sla, lifepo4

Batteries are the most common ways to power robots. The best choice of battery is usually LiPo. It allows for very high amp draw and lasts a long time.

Lipo batteries come with a certain number of cells, each of which is 3.7v but is usually charged to 4.2. For example a 3s \(s is for cell\) lipo is rated at 11.1v, but can be charged to 12.6v. Lipos can be dangerous. If they are shorted, they will blow up. [Heres](https://rogershobbycenter.com/lipoguide/) an article about lipos.

![](/assets/lipo.png)

SLA, sealed lead acid, batteries have very high capacity, and an extremely high momentary amp draw, but a very low continuous amp draw, which is why they are used to start cars.

![](/assets/slabattery.png)

NiMH batteries are getting kind of out of date these days, so only use them if a competiton \(\*cough\* Scioly \*cough\*\) disallows both lithium and lead batteries.

![](/assets/nimh.png)

Lithium Iron Phosphate, LiFePo4 batteries are pretty hipster these days, not many people have actually used them, they're just talked about a lot, so they have the potential to be pretty good.

![](/assets/lifepo4.png)

###### bec, regulators

Sometimes you need a different voltage that your battery puts out, which means you need a regulator. BEC, or battery eliminator circuit's are a good way of stepping down any voltage form 7-24 V to 5V. If you need something else, you will need a buck converter.

![](/assets/bec.png)

###### wall power

I do not recommend using wall power, it is dangerous, and difficult to use. If you do, use a PSU, and probably one from a reputable brand like Meanwell.

###### Connectors

Connectors to your batteries are useful so you can easily remove them when you want, but also they don't come unplugged accidentally.

XT-60 is my reccomended battery connector for anything decently sized. JST is acceptable for smaller sizes, but XT-60 is always a good option. Actually I've started to really like phoenix connections when you're dealing with really large amperages.

![](/assets/xt60.png)

-lmr

