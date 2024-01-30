# Berachain Node Build

## Setup

1. Rent a VPS from Alibaba Cloud, Baidu Cloud, or Bandwagon Host, or use an idle computer/server at home with a minimum of 16GB RAM, 200GB disk space, and a 6-core CPU. Install either Ubuntu 22.04 Server or Desktop. Enable the openssh service to complete the hardware setup.

2. Use FinalShell (or any other SSH tool) to log in to the server.

3. Install Go version 1.20 or higher. In this example, version 1.21.6 is used:

    ```bash
    cd ~
    wget https://go.dev/dl/go1.21.6.linux-amd64.tar.gz
    sudo tar -xzf go1.21.6.linux-amd64.tar.gz -C /usr/local/
    ```

4. Install the following software:

    ```bash
    sudo apt-get install golang jq -y
    echo 'export PATH=$PATH:/usr/local/go/bin' | tee -a ~/.bashrc
    echo 'export PATH=$PATH:$(go env GOPATH)/bin' | tee -a ~/.bashrc
    source ~/.bashrc
    ```

5. Install Foundry:

    ```bash
    curl -L https://foundry.paradigm.xyz | bash
    ```

6. Clone the source code and execute:

    ```bash
    cd ~
    git clone https://github.com/berachain/polaris
    cd polaris
    git checkout main
    make test-unit
    ```

## Start Testnet

7. Start the testnet:

    ```bash
    screen -S polaris
    cd ~/polaris
    make start
    ```

Upon successful execution, the provided interface should appear:

![image](https://github.com/tujj99/Berachain-Node-Build/assets/53027340/4ae8869b-225e-4ede-9750-a87b761d16a3)
