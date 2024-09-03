---
layout: project
type: project
image: img/SCEL/scel-logo.png
title: "SCEL firmware"
date: 2022
published: true
labels:
  - SQL
  - GitHub
  - Python
  - C
  - Linux
summary: "Vertically Integrated Project that focuses on the firmware of the weatherboxes produced by UH Manoa's SCEL lab."
---

<div style="width: 70%;">
  <img class="img-fluid" src="../img/SCEL/SCEL-people.png">
</div>

The Smart Campus Energy Lab, or SCEL, is a VIP (Vertically Integrated Project) at the University of Hawaii at Manoa. As a VIP, SCEL brings together students from various disciplines to tackle one of Hawaii's most pressing challenges: achieving 100% renewable energy by 2045. To accomplish this goal, SCEL aims to gather weather data and use it to predict weather patterns. This data can then be used to determine ideal locations for future renewable energy sources. SCEL comprises multiple teams. Team Apple and Team Guava form the hardware backbone, while the Firmware Team keeps the software running on the local servers and the weather boxes themselves. The Machine Learning Team is then in charge of using that data to predict weather patterns.

I was part of Team Firmware in the fall of 2022. We first dove headfirst into infrastructure, fixing the test server that was broken from the previous semester. After that, we got on our way to fine-tuning the server so that it could collect information from the weather boxes, as well as fixing and maintaining the database and gateway servers. Sometimes Team Apple or Team Guava would have a connection issue or something wrong with their version of the firmware, so we would help them troubleshoot. One of the biggest things we did was simplifying the data pipeline. This meant getting our hands dirty with SQL, command-line wizardry, and C programming to reshape the weatherbox schemas.

But SCEL isn't just about coding and data - it's a place for personal growth. Teamwork isn't just encouraged; it's essential. As the lab's go-to support crew, we've learned the art of clear communication and the power of synergy. Time management has become second nature in this fast-paced environment.

The technical skills I've gained are like tools in a Swiss Army knife - versatile and invaluable. SQL databases? Check. XBEE configuration for data transmission? Mastered. But perhaps the most valuable lesson is this: in the world of renewable energy, every line of code, every data point, and every team member plays a crucial role in building a greener future for Hawaii.
