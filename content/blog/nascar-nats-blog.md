+++
date = "2023-07-31"
draft = false
title = "NASCAR uses NATS to distribute real-time telemetry data"
author = "Jean-Noël Moyne"
categories = ["Community"]
tags = ["NATS"]
+++

<img alt="Appsecco Logo" src="https://www.nascar.com/wp-content/uploads/sites/7/2023/01/Footer_75thAnniversary_IDMark_rgb_OnDkBkgd-1-300x51-1.png" height="32" width="225">

How NASCAR uses NATS to deliver real-time racing data to broadcasters, racing teams, and fans

## Distributing live telemetry data

NASCAR's NextGen cars feature a host of changes including being fitted with a host of sensors generating 60 data points hundreds of times per second for the duration of the race.
This telemetry data is transmitted over UHF radio waves to the NASCAR mobile data center (literally a data center in a semi-truck trailer that goes to each track venue), where it is then ingested and retransmitted both to the racing teams and broadcasters on site at the track but also to the AWS cloud where it is both stored for historical analysis and re-distributed in real time to the team's back offices and to racing fans.

## Why NATS

This is real-time data generated at a high rate of speed (literally! :)) that it is imperative to transmit safely and with the lowest latency possible to the teams (amongst many other things, streaming sensor data can for example be used to predict mechanical failures as they are about to happen) both on site and over the cloud to their home-bases.

Besides latency and throughput, security was another important aspect: "One key feature of NATS incorporated in this design is isolation of the data between different subscribers (multi-tenancy). Ensuring that a given racing team is the only recipient of their car’s telemetry data is essential for competition integrity. Thus, teams who connect to the ERDP to receive live telemetry data are only able to access the appropriate data set for them, in real time."

## The article

Learn more about this in this very interesting AWS blog:

https://aws.amazon.com/blogs/media/accelerating-motorsports-how-nascar-delivers-real-time-racing-data-to-broadcasters-racing-teams-and-fans/
