---
title: "Github Actions"
author: "Agastya Patel"
categories: [Notes, Opss]
draft: false
---
Heirarchy
|-Events (PR, Push, Issue Created/Closed)
	|-Workflow
		|-Job 1\----------------------------------------Runner1 
			|- Step1: Action---------------------------|-Run Step->Log Result
			|- Step2: Shell Command-----------------|-Run Step->Log Result
			|- Step3: Action---------------------------|-Run Step->Log Result
		|-Job2-----------------------------------------Runner2
			|-Step1: Shell Command