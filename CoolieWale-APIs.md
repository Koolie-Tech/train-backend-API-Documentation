# CoolieWale-Train-APIs
This **Node.js Backend** code contains APIs for getting **PNR Status**, **Train Information** and **Live Train Running Status Information**.




## Table of Contents
- Understanding the API
  - PNR Status Routes
  - Train Information Routes
  - Live Train Running Status Information Routes




## Understanding the API

### PNR Status Routes
- GET & POST: `/getPNRinfo`
  - Description: Gives Information about PNR.
  - Input Query: `?pnr='actual-pnr'`
  - Output: [see json output format](http://ec2-3-109-210-229.ap-south-1.compute.amazonaws.com:5000/getPNRinfo?pnr=2635870632)


### Train Information Routes
- GET & POST: `/getTrainInfo`
  - Description: Gives Information about the train whose train number is provided.
  - Input Query: `?trainNo='actual-train-number'`
  - Output: [see json output format](http://ec2-3-109-210-229.ap-south-1.compute.amazonaws.com:5000/getTrainInfo?trainNo=12802)

- GET & POST: `/getTrainBtwStation`
    - Description: Gives all the trains info that runs between two provided stations.
    - Input Query: `?from='from-station-code'&to='to-station-code'`
    - Output: [see json output format](http://ec2-3-109-210-229.ap-south-1.compute.amazonaws.com:5000/getTrainBtwStation?from=NDLS&to=DOS)

- GET & POST: `/getTrainOnDate`
    - Description: Gives all the trains info that runs between two provided stations on the provided date (strictly follow date input format i.e. DD-MM-YYYY).
    - Input Query: `?from='from-station-code'&to='to-station-code'&date='DD-MM-YYYY'`
    - Output: [see json output format](http://ec2-3-109-210-229.ap-south-1.compute.amazonaws.com:5000/getTrainOnDate?from=NDLS&to=DOS&date=20-03-2024)

- GET & POST: `/getRoute`
    - Description: Gives the station list where the provided train stops.
    - Input Query: `?trainNo='actual-train-number'`
    - Output: [see json output format](http://ec2-3-109-210-229.ap-south-1.compute.amazonaws.com:5000/getRoute?trainNo=12802)


### Live Train Running Status Information Routes
- GET & POST: `/liveTrainInfo`
    - Description:
        1. Provide the `route` array which contains all the intermediate stations where the train doesn't stop and also the stations where it stops.
        2. Provide the `live status` array which contains information that tells whether a particular station is passed or not.
        3. Provide the `current` array that contains the current station code and its name.
    - Input Query: `?trainNo='actual-train-number'&date='DD-MMM-YYYY'`
    - Output: [see json output format](http://ec2-3-109-210-229.ap-south-1.compute.amazonaws.com:5000/liveTrainInfo?trainNo=12802&date=21-Mar-2024)
