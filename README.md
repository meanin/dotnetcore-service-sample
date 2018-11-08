# dotnetcore-service-sample
Sample .NET Core 2.1 service using generic host and handling SIGINT/SIGTERM

More details @ https://dejanstojanovic.net/aspnet/2018/june/clean-service-stop-on-linux-with-net-core-21/


# Edit: @meanin


1. build docker image in a solution folder:
	docker build -f Core.Service.Sample\Dockerfile -t "coreservicesample:latest" .
	
2. tested with sigterm:
	docker stop <containerid>
	
3. tested with sigkill:
	docker kill <containerid>