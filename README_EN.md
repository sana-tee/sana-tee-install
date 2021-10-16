This program is used for Sana mining, support no SGX and TEE function of computer mining, output and TEE mode is basically the same, a little difference may be due to equipment configuration high and low problems



## Use method

The first step is to know the normal RPC of Sana mining process, configure ant.yaml and so on



##a. Procedural



Run in the program directory

` ` `

sudo ./sanatee start --verbosity 5 --full-node --config /root/ant.yaml --debug-api-enable

` ` `





# b.d ocker way

1. Register first

/sanatee start --data-dir= your node directory --password= your password

Get the Ethereum Address to me and I'll give you the authorization code and machine code

A mykeys directory will be generated at the level of your keys directory with two files device.key and hahano.key. These files will be saved with your keys so you can use them next time



2. Use the Docker import function to import the Docker package

Docker load - i. / sanatee0.1.3. Tar



3. Rebuild the container using Docker





docker run -d --restart=always -p 1763:1633 -p 1764:1634 -p 1765:1635 -v /root/ant.yaml:/root/ant.yaml -v /data/013:/home/ant --name sana-013 Sana /tee:v0.1.3 start --verbosity 5 --full-node --config /root/ant.yaml --debug-api-enable