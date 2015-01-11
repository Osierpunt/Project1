# Project1

project1 <- read.table("household_power_consumption.txt", sep=";",dec=",", header=TRUE, stringsAsFactor=FALSE); project1 <- project1[66638:69517,]; project1$DateTime <- as.POSIXct(paste(project1$Date, project1$Time), format="%d/%m/%Y %H:%M:%S");

Plot1:
hist(project1$Global_active_power, main="Global Active Power", xlab="Global Active Power (kilowatts)", col="red")

Plot2:
plot(project1$DateTime,project1$Global_active_power,xlab="", ylab="Global Active Power (kilowatts)", type="l")

Plot3:
par(mar=c(2,10,2,10))
plot(project1$DateTime,project1$Sub_metering_1, type="l",xlab="",ylab="Energy sub metering")
lines(project1$DateTime,project1$Sub_metering_2, type="l",col="red")
lines(project1$DateTime,project1$Sub_metering_3, type="l",col="blue")
legend("topright",col=c("black","red","blue"),legend=c("Sub_metering_1","Sub_metering_2","Sub_metering_3"),lty=c(1,1))

Plot4:
par(mfrow=c(2,2), mar=c(4,8,4,8))
plot(project1$DateTime,project1$Global_active_power,xlab="", ylab="Global Active Power", type="l")
plot(project1$DateTime,project1$Voltage, ylab="Voltage",xlab="datetime", type="l")
plot(project1$DateTime,project1$Sub_metering_1, type="l",xlab="",ylab="Energy sub metering")
lines(project1$DateTime,project1$Sub_metering_2, type="l",col="red")
lines(project1$DateTime,project1$Sub_metering_3, type="l",col="blue")
legend("topright",col=c("black","red","blue"),legend=c("Sub_metering_1","Sub_metering_2","Sub_metering_3"),lty=c(1,1))
plot(project1$DateTime,project1$Global_reactive_power, type="l",xlab="datetime",ylab="Global_reactive_power")
