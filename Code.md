# Assignment-1-Exploratory-Data-Analysis
> house_a_data <-rbind(housedata[housedata$Date=="1/2/2007",],housedata[housedata$Date=="2/2/2007",])
> housedata <-read.table("household_power_consumption.txt", header=TRUE, sep=";", na.strings = "?")
> house_a_data <-rbind(housedata[housedata$Date=="1/2/2007",],housedata[housedata$Date=="2/2/2007",])
> house_a_data$Date <- as.Date(house_a_data$Date,"%d/%m/%Y")
> house_a_data<-cbind(house_a_data, "DateTime" = as.POSIXct(paste(house_a_data$Date, house_a_data$Time)))
> 
> hist(as.numeric(house_a_data$Global_active_power), col="Red", main="Global Active Power", xlab="Global Active power (kilowatts)", ylab="Frequency")
> plot(house_a_data$Global_active_power ~ house_a_data$DateTime, type="l", xlab= "", ylab="Global Active power (kilowatts)")
> with(house_a_data, {plot(Sub_metering_1 ~ DateTime, type="l", xlab= "", ylab="Energy Sub Metering")})
> 
> lines(house_a_data$Sub_metering_2 ~ house_a_data$DateTime, col = 'Red')
> lines(house_a_data$Sub_metering_3 ~ house_a_data$DateTime, col = 'Blue')
> legend("topright", lty=1, lwd =3, col=c("black","red","blue") ,legend=c("Sub_metering_1","Sub_metering_2","Sub_metering_3"))
> par(mfrow=c(2,2))
> plot(house_a_data$Global_active_power ~ house_a_data$DateTime, type="l")
> plot(house_a_data$Voltage ~ house_a_data$DateTime, type="l")
> 
> with(house_a_data, {plot(Sub_metering_1 ~ DateTime, type="l")})
> lines(house_a_data$Sub_metering_2 ~ house_a_data$DateTime, col = 'Red')
> lines(house_a_data$Sub_metering_3 ~ house_a_data$DateTime, col = 'Blue')
> 
> plot(house_a_data$Global_reactive_power ~ house_a_data$DateTime, type="l")
