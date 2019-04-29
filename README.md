# Jedis-lock [![Build Status](https://travis-ci.org/MarbleNetwork/jedis-lock.svg?branch=master)](https://travis-ci.org/MarbleNetwork/jedis-lock) [ ![Download](https://api.bintray.com/packages/jordanwwood/MarbleNetworkMvn/JedisLock/images/download.svg) ](https://bintray.com/jordanwwood/MarbleNetworkMvn/JedisLock/_latestVersion)

Jedis-lock is easy to use and simple implementation of distributed lock using Redis database and Jedis driver.

## How do I use it?

You can download the latests build at:
    https://github.com/MarbleNetwork/jedis-lock/releases

Or use it as a maven dependency:
    <repository>
		<id>MarbleNetwork</id>
		<url>https://dl.bintray.com/jordanwwood/MarbleNetworkMvn</url>
		<snapshots>
			<enabled>true</enabled>
		</snapshots>
	</repository>

    <dependency>
        <groupId>com.github.jedis-lock</groupId>
        <artifactId>jedis-lock</artifactId>
        <version>1.0.1</version>
        <type>jar</type>
        <scope>compile</scope>
    </dependency>

To use it just:

    Jedis jedis = new Jedis("localhost");
    JedisLock lock = new JedisLock(jedis, "lockname", 10000, 30000);
    lock.acquire();
    try {
      // do some stuff
    }
    finally {
      lock.release();
    }

That's it.

## License

The Apache Software License, Version 2.0
