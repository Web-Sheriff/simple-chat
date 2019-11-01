# Assignment. DS. Week 11
Hi there! Look at pretty simple chat application in nodejs and mongodb :)

I used next tutorials in this assignment:
* https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/#install-mongodb-community-edition-using-deb-packages
* https://docs.mongodb.com/manual/tutorial/deploy-replica-set/
* https://medium.com/@amkurian/simple-chat-application-in-node-js-using-express-mongoose-and-socket-io-ee62d94f5804

## rs.status()
``` 
rs0:PRIMARY> rs.status()
{
	"set" : "rs0",
	"date" : ISODate("2019-11-01T09:48:09.550Z"),
	"myState" : 1,
	"term" : NumberLong(1),
	"syncingTo" : "",
	"syncSourceHost" : "",
	"syncSourceId" : -1,
	"heartbeatIntervalMillis" : NumberLong(2000),
	"majorityVoteCount" : 2,
	"writeMajorityCount" : 2,
	"optimes" : {
		"lastCommittedOpTime" : {
			"ts" : Timestamp(1572601688, 1),
			"t" : NumberLong(1)
		},
		"lastCommittedWallTime" : ISODate("2019-11-01T09:48:08.085Z"),
		"readConcernMajorityOpTime" : {
			"ts" : Timestamp(1572601688, 1),
			"t" : NumberLong(1)
		},
		"readConcernMajorityWallTime" : ISODate("2019-11-01T09:48:08.085Z"),
		"appliedOpTime" : {
			"ts" : Timestamp(1572601688, 1),
			"t" : NumberLong(1)
		},
		"durableOpTime" : {
			"ts" : Timestamp(1572601688, 1),
			"t" : NumberLong(1)
		},
		"lastAppliedWallTime" : ISODate("2019-11-01T09:48:08.085Z"),
		"lastDurableWallTime" : ISODate("2019-11-01T09:48:08.085Z")
	},
	"lastStableRecoveryTimestamp" : Timestamp(1572601658, 1),
	"lastStableCheckpointTimestamp" : Timestamp(1572601658, 1),
	"electionCandidateMetrics" : {
		"lastElectionReason" : "electionTimeout",
		"lastElectionDate" : ISODate("2019-11-01T09:17:36.823Z"),
		"termAtElection" : NumberLong(1),
		"lastCommittedOpTimeAtElection" : {
			"ts" : Timestamp(0, 0),
			"t" : NumberLong(-1)
		},
		"lastSeenOpTimeAtElection" : {
			"ts" : Timestamp(1572599846, 1),
			"t" : NumberLong(-1)
		},
		"numVotesNeeded" : 2,
		"priorityAtElection" : 1,
		"electionTimeoutMillis" : NumberLong(10000),
		"numCatchUpOps" : NumberLong(1818653285),
		"newTermStartDate" : ISODate("2019-11-01T09:17:37.738Z"),
		"wMajorityWriteAvailabilityDate" : ISODate("2019-11-01T09:17:38.288Z")
	},
	"members" : [
		{
			"_id" : 0,
			"name" : "server1:27017",
			"ip" : "78.47.120.185",
			"health" : 1,
			"state" : 1,
			"stateStr" : "PRIMARY",
			"uptime" : 2126,
			"optime" : {
				"ts" : Timestamp(1572601688, 1),
				"t" : NumberLong(1)
			},
			"optimeDate" : ISODate("2019-11-01T09:48:08Z"),
			"syncingTo" : "",
			"syncSourceHost" : "",
			"syncSourceId" : -1,
			"infoMessage" : "",
			"electionTime" : Timestamp(1572599856, 1),
			"electionDate" : ISODate("2019-11-01T09:17:36Z"),
			"configVersion" : 1,
			"self" : true,
			"lastHeartbeatMessage" : ""
		},
		{
			"_id" : 1,
			"name" : "server2:27017",
			"ip" : "78.47.120.184",
			"health" : 1,
			"state" : 2,
			"stateStr" : "SECONDARY",
			"uptime" : 1842,
			"optime" : {
				"ts" : Timestamp(1572601688, 1),
				"t" : NumberLong(1)
			},
			"optimeDurable" : {
				"ts" : Timestamp(1572601688, 1),
				"t" : NumberLong(1)
			},
			"optimeDate" : ISODate("2019-11-01T09:48:08Z"),
			"optimeDurableDate" : ISODate("2019-11-01T09:48:08Z"),
			"lastHeartbeat" : ISODate("2019-11-01T09:48:09.446Z"),
			"lastHeartbeatRecv" : ISODate("2019-11-01T09:48:08.474Z"),
			"pingMs" : NumberLong(1),
			"lastHeartbeatMessage" : "",
			"syncingTo" : "server1:27017",
			"syncSourceHost" : "server1:27017",
			"syncSourceId" : 0,
			"infoMessage" : "",
			"configVersion" : 1
		},
		{
			"_id" : 2,
			"name" : "server3:27017",
			"ip" : "78.47.120.186",
			"health" : 1,
			"state" : 2,
			"stateStr" : "SECONDARY",
			"uptime" : 1842,
			"optime" : {
				"ts" : Timestamp(1572601688, 1),
				"t" : NumberLong(1)
			},
			"optimeDurable" : {
				"ts" : Timestamp(1572601688, 1),
				"t" : NumberLong(1)
			},
			"optimeDate" : ISODate("2019-11-01T09:48:08Z"),
			"optimeDurableDate" : ISODate("2019-11-01T09:48:08Z"),
			"lastHeartbeat" : ISODate("2019-11-01T09:48:09.395Z"),
			"lastHeartbeatRecv" : ISODate("2019-11-01T09:48:07.973Z"),
			"pingMs" : NumberLong(0),
			"lastHeartbeatMessage" : "",
			"syncingTo" : "server1:27017",
			"syncSourceHost" : "server1:27017",
			"syncSourceId" : 0,
			"infoMessage" : "",
			"configVersion" : 1
		}
	],
	"ok" : 1,
	"$clusterTime" : {
		"clusterTime" : Timestamp(1572601688, 1),
		"signature" : {
			"hash" : BinData(0,"AAAAAAAAAAAAAAAAAAAAAAAAAAA="),
			"keyId" : NumberLong(0)
		}
	},
	"operationTime" : Timestamp(1572601688, 1)
}
```

## rs.config()
```
rs0:PRIMARY> rs.config() 
{
	"_id" : "rs0",
	"version" : 1,
	"protocolVersion" : NumberLong(1),
	"writeConcernMajorityJournalDefault" : true,
	"members" : [
		{
			"_id" : 0,
			"host" : "server1:27017",
			"arbiterOnly" : false,
			"buildIndexes" : true,
			"hidden" : false,
			"priority" : 1,
			"tags" : {
				
			},
			"slaveDelay" : NumberLong(0),
			"votes" : 1
		},
		{
			"_id" : 1,
			"host" : "server2:27017",
			"arbiterOnly" : false,
			"buildIndexes" : true,
			"hidden" : false,
			"priority" : 1,
			"tags" : {
				
			},
			"slaveDelay" : NumberLong(0),
			"votes" : 1
		},
		{
			"_id" : 2,
			"host" : "server3:27017",
			"arbiterOnly" : false,
			"buildIndexes" : true,
			"hidden" : false,
			"priority" : 1,
			"tags" : {
				
			},
			"slaveDelay" : NumberLong(0),
			"votes" : 1
		}
	],
	"settings" : {
		"chainingAllowed" : true,
		"heartbeatIntervalMillis" : 2000,
		"heartbeatTimeoutSecs" : 10,
		"electionTimeoutMillis" : 10000,
		"catchUpTimeoutMillis" : -1,
		"catchUpTakeoverDelayMillis" : 30000,
		"getLastErrorModes" : {
			
		},
		"getLastErrorDefaults" : {
			"w" : 1,
			"wtimeout" : 0
		},
		"replicaSetId" : ObjectId("5dbbf826fad449b416736bc1")
	}
}
```
## Screenshot
![](https://i.imgur.com/0zbe3sR.png)

## rs.status()
```
rs0:PRIMARY> rs.status()
{
	"set" : "rs0",
	"date" : ISODate("2019-11-01T10:58:27.308Z"),
	"myState" : 1,
	"term" : NumberLong(2),
	"syncingTo" : "",
	"syncSourceHost" : "",
	"syncSourceId" : -1,
	"heartbeatIntervalMillis" : NumberLong(2000),
	"majorityVoteCount" : 2,
	"writeMajorityCount" : 2,
	"optimes" : {
		"lastCommittedOpTime" : {
			"ts" : Timestamp(1572605901, 1),
			"t" : NumberLong(2)
		},
		"lastCommittedWallTime" : ISODate("2019-11-01T10:58:21.291Z"),
		"readConcernMajorityOpTime" : {
			"ts" : Timestamp(1572605901, 1),
			"t" : NumberLong(2)
		},
		"readConcernMajorityWallTime" : ISODate("2019-11-01T10:58:21.291Z"),
		"appliedOpTime" : {
			"ts" : Timestamp(1572605901, 1),
			"t" : NumberLong(2)
		},
		"durableOpTime" : {
			"ts" : Timestamp(1572605901, 1),
			"t" : NumberLong(2)
		},
		"lastAppliedWallTime" : ISODate("2019-11-01T10:58:21.291Z"),
		"lastDurableWallTime" : ISODate("2019-11-01T10:58:21.291Z")
	},
	"lastStableRecoveryTimestamp" : Timestamp(1572605858, 1),
	"lastStableCheckpointTimestamp" : Timestamp(1572605858, 1),
	"electionCandidateMetrics" : {
		"lastElectionReason" : "electionTimeout",
		"lastElectionDate" : ISODate("2019-11-01T10:58:20.357Z"),
		"termAtElection" : NumberLong(2),
		"lastCommittedOpTimeAtElection" : {
			"ts" : Timestamp(1572605888, 1),
			"t" : NumberLong(1)
		},
		"lastSeenOpTimeAtElection" : {
			"ts" : Timestamp(1572605888, 1),
			"t" : NumberLong(1)
		},
		"numVotesNeeded" : 2,
		"priorityAtElection" : 1,
		"electionTimeoutMillis" : NumberLong(10000),
		"priorPrimaryMemberId" : 0,
		"numCatchUpOps" : NumberLong(27017),
		"newTermStartDate" : ISODate("2019-11-01T10:58:21.291Z"),
		"wMajorityWriteAvailabilityDate" : ISODate("2019-11-01T10:58:26.373Z")
	},
	"members" : [
		{
			"_id" : 0,
			"name" : "server1:27017",
			"ip" : "78.47.120.185",
			"health" : 0,
			"state" : 8,
			"stateStr" : "(not reachable/healthy)",
			"uptime" : 0,
			"optime" : {
				"ts" : Timestamp(0, 0),
				"t" : NumberLong(-1)
			},
			"optimeDurable" : {
				"ts" : Timestamp(0, 0),
				"t" : NumberLong(-1)
			},
			"optimeDate" : ISODate("1970-01-01T00:00:00Z"),
			"optimeDurableDate" : ISODate("1970-01-01T00:00:00Z"),
			"lastHeartbeat" : ISODate("2019-11-01T10:58:21.092Z"),
			"lastHeartbeatRecv" : ISODate("2019-11-01T10:58:09.759Z"),
			"pingMs" : NumberLong(0),
			"lastHeartbeatMessage" : "Couldn't get a connection within the time limit",
			"syncingTo" : "",
			"syncSourceHost" : "",
			"syncSourceId" : -1,
			"infoMessage" : "",
			"configVersion" : -1
		},
		{
			"_id" : 1,
			"name" : "server2:27017",
			"ip" : "78.47.120.184",
			"health" : 1,
			"state" : 1,
			"stateStr" : "PRIMARY",
			"uptime" : 6154,
			"optime" : {
				"ts" : Timestamp(1572605901, 1),
				"t" : NumberLong(2)
			},
			"optimeDate" : ISODate("2019-11-01T10:58:21Z"),
			"syncingTo" : "",
			"syncSourceHost" : "",
			"syncSourceId" : -1,
			"infoMessage" : "",
			"electionTime" : Timestamp(1572605900, 1),
			"electionDate" : ISODate("2019-11-01T10:58:20Z"),
			"configVersion" : 1,
			"self" : true,
			"lastHeartbeatMessage" : ""
		},
		{
			"_id" : 2,
			"name" : "server3:27017",
			"ip" : "78.47.120.186",
			"health" : 1,
			"state" : 2,
			"stateStr" : "SECONDARY",
			"uptime" : 6060,
			"optime" : {
				"ts" : Timestamp(1572605901, 1),
				"t" : NumberLong(2)
			},
			"optimeDurable" : {
				"ts" : Timestamp(1572605901, 1),
				"t" : NumberLong(2)
			},
			"optimeDate" : ISODate("2019-11-01T10:58:21Z"),
			"optimeDurableDate" : ISODate("2019-11-01T10:58:21Z"),
			"lastHeartbeat" : ISODate("2019-11-01T10:58:26.373Z"),
			"lastHeartbeatRecv" : ISODate("2019-11-01T10:58:25.769Z"),
			"pingMs" : NumberLong(0),
			"lastHeartbeatMessage" : "",
			"syncingTo" : "server2:27017",
			"syncSourceHost" : "server2:27017",
			"syncSourceId" : 1,
			"infoMessage" : "",
			"configVersion" : 1
		}
	],
	"ok" : 1,
	"$clusterTime" : {
		"clusterTime" : Timestamp(1572605901, 1),
		"signature" : {
			"hash" : BinData(0,"AAAAAAAAAAAAAAAAAAAAAAAAAAA="),
			"keyId" : NumberLong(0)
		}
	},
	"operationTime" : Timestamp(1572605901, 1)
}
```

## rs.config()
```
rs0:PRIMARY> rs.config()
{
	"_id" : "rs0",
	"version" : 1,
	"protocolVersion" : NumberLong(1),
	"writeConcernMajorityJournalDefault" : true,
	"members" : [
		{
			"_id" : 0,
			"host" : "server1:27017",
			"arbiterOnly" : false,
			"buildIndexes" : true,
			"hidden" : false,
			"priority" : 1,
			"tags" : {
				
			},
			"slaveDelay" : NumberLong(0),
			"votes" : 1
		},
		{
			"_id" : 1,
			"host" : "server2:27017",
			"arbiterOnly" : false,
			"buildIndexes" : true,
			"hidden" : false,
			"priority" : 1,
			"tags" : {
				
			},
			"slaveDelay" : NumberLong(0),
			"votes" : 1
		},
		{
			"_id" : 2,
			"host" : "server3:27017",
			"arbiterOnly" : false,
			"buildIndexes" : true,
			"hidden" : false,
			"priority" : 1,
			"tags" : {
				
			},
			"slaveDelay" : NumberLong(0),
			"votes" : 1
		}
	],
	"settings" : {
		"chainingAllowed" : true,
		"heartbeatIntervalMillis" : 2000,
		"heartbeatTimeoutSecs" : 10,
		"electionTimeoutMillis" : 10000,
		"catchUpTimeoutMillis" : -1,
		"catchUpTakeoverDelayMillis" : 30000,
		"getLastErrorModes" : {
			
		},
		"getLastErrorDefaults" : {
			"w" : 1,
			"wtimeout" : 0
		},
		"replicaSetId" : ObjectId("5dbbf826fad449b416736bc1")
	}
}
```

## Screenshot after
![](https://i.imgur.com/bumfoB7.png)
