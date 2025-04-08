#Index.md Web Space

<b>ETH Mainnet Contract Analysis</b>

Etherscan.io smart contract for security analysis:
https://etherscan.io/address/0xdac17f958d2ee523a2206206994597c13d831ec7#code

Contract Address:
0xdAC17F958D2ee523a2206206994597C13D831ec7

Github Review:
https://github.com/ethereum/EIPs/issues/20

<b>Fix for ERC20 short address attack</b>

This part of the example code requres the address to be of correct length. If the length is incorrect, say by one int, then an appended 0 can cause the funds to be redirected incorrectly or fail and become permanently locked.

   /**
    * @dev Fix for the ERC20 short address attack.
    */
    modifier onlyPayloadSize(uint size) {
        require(!(msg.data.length < size + 4));
        _;
    }