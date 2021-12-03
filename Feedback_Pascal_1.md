```bash
Warning: Unused function parameter. Remove or comment out the variable name to silence this warning.
   --> contracts/LiquidityProtectionMultipleLimitsStrategy.sol:101:63:
    |
101 |     function isTransferAllowed(address token, address sender, address recipient, uint256 amount) external {
    |                                                               ^^^^^^^^^^^^^^^^^


Warning: Unused function parameter. Remove or comment out the variable name to silence this warning.
  --> contracts/LiquidityProtectionSingleLimitStrategy.sol:85:63:
   |
85 |     function isTransferAllowed(address token, address sender, address recipient, uint256 amount) external {
   |                                                               ^^^^^^^^^^^^^^^^^


Warning: Unused function parameter. Remove or comment out the variable name to silence this warning.
  --> contracts/TreasuryProtectionStrategy.sol:29:82:
   |
29 |     function isTransferAllowed(address token, address sender, address recipient, uint256 amount) external view {
   |                                                                                  ^^^^^^^^^^^^^^


Warning: Unused function parameter. Remove or comment out the variable name to silence this warning.
   --> contracts/LosslessControllerV2.sol:151:33:
    |
151 |     function beforeTransferFrom(address msgSender, address sender, address recipient, uint256 amount) external {
    |                                 ^^^^^^^^^^^^^^^^^




PausableUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol#97) shadows:
        - ContextUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/utils/ContextUpgradeable.sol#31)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#state-variable-shadowing

Contract locking ether found:
        Contract LERC20Mock (contracts/LERC20Mock.sol#6-33) has payable functions:
         - LERC20Mock.constructor(uint256,string,string,address,uint256,address,address,address,uint256) (contracts/LERC20Mock.sol#7-19)
        But does not have a function to withdraw the ether
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#contracts-that-lock-ether

TreasuryProtectionStrategy.removeProtectedAddresses(address,address[]) (contracts/TreasuryProtectionStrategy.sol#45-51) deletes TreasuryProtectionStrategy.Whitelist (contracts/TreasuryProtectionStrategy.sol#9-11) which contains a mapping:
        -delete protectedAddresses[token].protection[addressesToRemove[i]] (contracts/TreasuryProtectionStrategy.sol#47)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#deletion-on-mapping-containing-a-structure

LiquidityProtectionMultipleLimitsStrategy.saveLimits(address,address,uint256[],uint256[],uint256[]).limit (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#133) is a local variable never initialized
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#uninitialized-local-variables

LERC20Mock.constructor(uint256,string,string,address,uint256,address,address,address,uint256).totalSupply (contracts/LERC20Mock.sol#8) shadows:
        - LERC20.totalSupply() (contracts/LERC20.sol#188-190) (function)
        - IERC20.totalSupply() (contracts/LERC20.sol#16) (function)
LERC20Mock.constructor(uint256,string,string,address,uint256,address,address,address,uint256).name (contracts/LERC20Mock.sol#9) shadows:
        - LERC20.name() (contracts/LERC20.sol#176-178) (function)
LERC20Mock.constructor(uint256,string,string,address,uint256,address,address,address,uint256).symbol (contracts/LERC20Mock.sol#10) shadows:
        - LERC20.symbol() (contracts/LERC20.sol#180-182) (function)
LERC20Mock.constructor(uint256,string,string,address,uint256,address,address,address,uint256).admin (contracts/LERC20Mock.sol#14) shadows:
        - LERC20.admin (contracts/LERC20.sol#55) (state variable)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#local-variable-shadowing

LERC20.constructor(uint256,string,string,address,address,uint256,address).admin_ (contracts/LERC20.sol#69) lacks a zero-check on :
                - admin = admin_ (contracts/LERC20.sol#73)
LERC20.constructor(uint256,string,string,address,address,uint256,address).recoveryAdmin_ (contracts/LERC20.sol#69) lacks a zero-check on :
                - recoveryAdmin = recoveryAdmin_ (contracts/LERC20.sol#74)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#missing-zero-address-validation

LosslessControllerV1.initialize(address,address,address)._admin (contracts/LosslessControllerV1.sol#29) lacks a zero-check on :
                - admin = _admin (contracts/LosslessControllerV1.sol#30)
LosslessControllerV1.initialize(address,address,address)._recoveryAdmin (contracts/LosslessControllerV1.sol#29) lacks a zero-check on :
                - recoveryAdmin = _recoveryAdmin (contracts/LosslessControllerV1.sol#31)
LosslessControllerV1.initialize(address,address,address)._pauseAdmin (contracts/LosslessControllerV1.sol#29) lacks a zero-check on :
                - pauseAdmin = _pauseAdmin (contracts/LosslessControllerV1.sol#32)
LosslessControllerV1.setAdmin(address).newAdmin (contracts/LosslessControllerV1.sol#47) lacks a zero-check on :
                - admin = newAdmin (contracts/LosslessControllerV1.sol#49)
LosslessControllerV1.setRecoveryAdmin(address).newRecoveryAdmin (contracts/LosslessControllerV1.sol#52) lacks a zero-check on :
                - recoveryAdmin = newRecoveryAdmin (contracts/LosslessControllerV1.sol#54)
LosslessControllerV1.setPauseAdmin(address).newPauseAdmin (contracts/LosslessControllerV1.sol#57) lacks a zero-check on :
                - pauseAdmin = newPauseAdmin (contracts/LosslessControllerV1.sol#59)
LosslessControllerV2.setGuardian(address).newGuardian (contracts/LosslessControllerV2.sol#116) lacks a zero-check on :
                - guardian = newGuardian (contracts/LosslessControllerV2.sol#118)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#missing-zero-address-validation

LiquidityProtectionMultipleLimitsStrategy.setLimitsBatched(address,address[],uint256[],uint256[],uint256[]) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#45-56) has external calls inside a loop: guardian.setProtectedAddress(token,protectedAddresses[i]) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#53)
LiquidityProtectionMultipleLimitsStrategy.removeLimits(address,address[]) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#58-63) has external calls inside a loop: guardian.removeProtectedAddresses(token,protectedAddresses[i]) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#61)
LiquidityProtectionSingleLimitStrategy.setLimitBatched(address,address[],uint256,uint256,uint256) (contracts/LiquidityProtectionSingleLimitStrategy.sol#37-48) has external calls inside a loop: guardian.setProtectedAddress(token,protectedAddresses[i]) (contracts/LiquidityProtectionSingleLimitStrategy.sol#46)
LiquidityProtectionSingleLimitStrategy.removeLimits(address,address[]) (contracts/LiquidityProtectionSingleLimitStrategy.sol#64-69) has external calls inside a loop: guardian.removeProtectedAddresses(token,protectedAddresses[i]) (contracts/LiquidityProtectionSingleLimitStrategy.sol#67)
TreasuryProtectionStrategy.removeProtectedAddresses(address,address[]) (contracts/TreasuryProtectionStrategy.sol#45-51) has external calls inside a loop: guardian.removeProtectedAddresses(token,addressesToRemove[i]) (contracts/TreasuryProtectionStrategy.sol#48)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation/#calls-inside-a-loop

Reentrancy in LERC20.approve(address,uint256) (contracts/LERC20.sol#205-209):
        External calls:
        - lssAprove(spender,amount) (contracts/LERC20.sol#205)
                - lossless.beforeApprove(_msgSender(),spender,amount) (contracts/LERC20.sol#83)
        State variables written after the call(s):
        - _approve(_msgSender(),spender,amount) (contracts/LERC20.sol#207)
                - _allowances[owner][spender] = amount (contracts/LERC20.sol#258)
Reentrancy in LERC20.decreaseAllowance(address,uint256) (contracts/LERC20.sol#226-232):
        External calls:
        - lssDecreaseAllowance(spender,subtractedValue) (contracts/LERC20.sol#226)
                - lossless.beforeDecreaseAllowance(_msgSender(),spender,subtractedValue) (contracts/LERC20.sol#111)
        State variables written after the call(s):
        - _approve(_msgSender(),spender,currentAllowance - subtractedValue) (contracts/LERC20.sol#229)
                - _allowances[owner][spender] = amount (contracts/LERC20.sol#258)
Reentrancy in LERC20.increaseAllowance(address,uint256) (contracts/LERC20.sol#221-224):
        External calls:
        - lssIncreaseAllowance(spender,addedValue) (contracts/LERC20.sol#221)
                - lossless.beforeIncreaseAllowance(_msgSender(),spender,addedValue) (contracts/LERC20.sol#104)
        State variables written after the call(s):
        - _approve(_msgSender(),spender,_allowances[_msgSender()][spender] + addedValue) (contracts/LERC20.sol#222)
                - _allowances[owner][spender] = amount (contracts/LERC20.sol#258)
Reentrancy in LERC20.transfer(address,uint256) (contracts/LERC20.sol#196-199):
        External calls:
        - lssTransfer(recipient,amount) (contracts/LERC20.sol#196)
                - lossless.beforeTransfer(_msgSender(),recipient,amount) (contracts/LERC20.sol#90)
        State variables written after the call(s):
        - _transfer(_msgSender(),recipient,amount) (contracts/LERC20.sol#197)
                - _balances[sender] = senderBalance - amount (contracts/LERC20.sol#240)
                - _balances[recipient] += amount (contracts/LERC20.sol#241)
Reentrancy in LERC20.transferFrom(address,address,uint256) (contracts/LERC20.sol#211-219):
        External calls:
        - lssTransferFrom(sender,recipient,amount) (contracts/LERC20.sol#211)
                - lossless.beforeTransferFrom(_msgSender(),sender,recipient,amount) (contracts/LERC20.sol#97)
        State variables written after the call(s):
        - _approve(sender,_msgSender(),currentAllowance - amount) (contracts/LERC20.sol#216)
                - _allowances[owner][spender] = amount (contracts/LERC20.sol#258)
        - _transfer(sender,recipient,amount) (contracts/LERC20.sol#212)
                - _balances[sender] = senderBalance - amount (contracts/LERC20.sol#240)
                - _balances[recipient] += amount (contracts/LERC20.sol#241)
Reentrancy in LosslessGuardian.verifyAddress(address,address,bool) (contracts/LosslessGuardian.sol#78-81):
        External calls:
        - onlyLosslessAdmin() (contracts/LosslessGuardian.sol#78)
                - require(bool,string)(msg.sender == lossless.admin(),LOSSLESS: Not lossless admin) (contracts/LosslessGuardian.sol#41)
        State variables written after the call(s):
        - verifiedAddresses[token].verified[verifiedAddress] = value (contracts/LosslessGuardian.sol#79)
Reentrancy in LosslessGuardian.verifyStrategies(address[],bool) (contracts/LosslessGuardian.sol#64-69):
        External calls:
        - onlyLosslessAdmin() (contracts/LosslessGuardian.sol#64)
                - require(bool,string)(msg.sender == lossless.admin(),LOSSLESS: Not lossless admin) (contracts/LosslessGuardian.sol#41)
        State variables written after the call(s):
        - verifiedStrategies[strategies[i]] = value (contracts/LosslessGuardian.sol#66)
Reentrancy in LosslessGuardian.verifyToken(address,bool) (contracts/LosslessGuardian.sol#72-75):
        External calls:
        - onlyLosslessAdmin() (contracts/LosslessGuardian.sol#72)
                - require(bool,string)(msg.sender == lossless.admin(),LOSSLESS: Not lossless admin) (contracts/LosslessGuardian.sol#41)
        State variables written after the call(s):
        - verifiedTokens[token] = value (contracts/LosslessGuardian.sol#73)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#reentrancy-vulnerabilities-2

Reentrancy in LiquidityProtectionMultipleLimitsStrategy.pause(address,address) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#67-81):
        External calls:
        - onlyProtectionAdmin(token) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#67)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        State variables written after the call(s):
        - limits.push(cloneLimit(0,limits)) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#74)
Reentrancy in LiquidityProtectionSingleLimitStrategy.pause(address,address) (contracts/LiquidityProtectionSingleLimitStrategy.sol#74-80):
        External calls:
        - onlyProtectionAdmin(token) (contracts/LiquidityProtectionSingleLimitStrategy.sol#74)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        State variables written after the call(s):
        - limit.amountLeftInCurrentPeriod = 0 (contracts/LiquidityProtectionSingleLimitStrategy.sol#77)
        - limit.lastCheckpointTime = type()(uint256).max - limit.periodInSeconds (contracts/LiquidityProtectionSingleLimitStrategy.sol#78)
Reentrancy in LiquidityProtectionMultipleLimitsStrategy.removeLimits(address,address[]) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#58-63):
        External calls:
        - onlyProtectionAdmin(token) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#58)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        State variables written after the call(s):
        - delete protection[token].limits[protectedAddresses[i]] (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#60)
Reentrancy in LiquidityProtectionSingleLimitStrategy.removeLimits(address,address[]) (contracts/LiquidityProtectionSingleLimitStrategy.sol#64-69):
        External calls:
        - onlyProtectionAdmin(token) (contracts/LiquidityProtectionSingleLimitStrategy.sol#64)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        State variables written after the call(s):
        - delete protection[token].limits[protectedAddresses[i]] (contracts/LiquidityProtectionSingleLimitStrategy.sol#66)
Reentrancy in TreasuryProtectionStrategy.removeProtectedAddresses(address,address[]) (contracts/TreasuryProtectionStrategy.sol#45-51):
        External calls:
        - onlyProtectionAdmin(token) (contracts/TreasuryProtectionStrategy.sol#45)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        State variables written after the call(s):
        - delete protectedAddresses[token].protection[addressesToRemove[i]] (contracts/TreasuryProtectionStrategy.sol#47)
Reentrancy in StrategyBase.setGuardian(Guardian) (contracts/StrategyBase.sol#43-47):
        External calls:
        - require(bool,string)(msg.sender == controller.admin(),LOSSLESS: Not lossless admin) (contracts/StrategyBase.sol#44)
        State variables written after the call(s):
        - guardian = newGuardian (contracts/StrategyBase.sol#45)
Reentrancy in LiquidityProtectionSingleLimitStrategy.setLimit(address,address,uint256,uint256,uint256) (contracts/LiquidityProtectionSingleLimitStrategy.sol#52-62):       
        External calls:
        - onlyProtectionAdmin(token) (contracts/LiquidityProtectionSingleLimitStrategy.sol#58)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        State variables written after the call(s):
        - saveLimit(token,protectedAddress,periodInSeconds,amountPerPeriod,startTimestamp) (contracts/LiquidityProtectionSingleLimitStrategy.sol#60)
                - limit.periodInSeconds = periodInSeconds (contracts/LiquidityProtectionSingleLimitStrategy.sol#112)
                - limit.amountPerPeriod = amountPerPeriod (contracts/LiquidityProtectionSingleLimitStrategy.sol#113)
                - limit.lastCheckpointTime = startTimestamp (contracts/LiquidityProtectionSingleLimitStrategy.sol#114)
                - limit.amountLeftInCurrentPeriod = amountPerPeriod (contracts/LiquidityProtectionSingleLimitStrategy.sol#115)
Reentrancy in LiquidityProtectionSingleLimitStrategy.setLimitBatched(address,address[],uint256,uint256,uint256) (contracts/LiquidityProtectionSingleLimitStrategy.sol#37-48):
        External calls:
        - onlyProtectionAdmin(token) (contracts/LiquidityProtectionSingleLimitStrategy.sol#43)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        State variables written after the call(s):
        - saveLimit(token,protectedAddresses[i],periodInSeconds,amountPerPeriod,startTimestamp) (contracts/LiquidityProtectionSingleLimitStrategy.sol#45)
                - limit.periodInSeconds = periodInSeconds (contracts/LiquidityProtectionSingleLimitStrategy.sol#112)
                - limit.amountPerPeriod = amountPerPeriod (contracts/LiquidityProtectionSingleLimitStrategy.sol#113)
                - limit.lastCheckpointTime = startTimestamp (contracts/LiquidityProtectionSingleLimitStrategy.sol#114)
                - limit.amountLeftInCurrentPeriod = amountPerPeriod (contracts/LiquidityProtectionSingleLimitStrategy.sol#115)
Reentrancy in LiquidityProtectionMultipleLimitsStrategy.setLimits(address,address,uint256[],uint256[],uint256[]) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#27-36):
        External calls:
        - guardian.setProtectedAddress(token,protectedAddress) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#34)
        - onlyProtectionAdmin(token) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#33)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        State variables written after the call(s):
        - saveLimits(token,protectedAddress,periodsInSeconds,amountsPerPeriod,startTimestamp) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#35)
                - limits.push(limit) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#138)
Reentrancy in LiquidityProtectionMultipleLimitsStrategy.setLimitsBatched(address,address[],uint256[],uint256[],uint256[]) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#45-56):
        External calls:
        - guardian.setProtectedAddress(token,protectedAddresses[i]) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#53)
        - onlyProtectionAdmin(token) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#51)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        State variables written after the call(s):
        - saveLimits(token,protectedAddresses[i],periodsInSeconds,amountsPerPeriod,startTimestamp) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#54)
                - limits.push(limit) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#138)
Reentrancy in TreasuryProtectionStrategy.setProtectedAddress(address,address,address[]) (contracts/TreasuryProtectionStrategy.sol#36-42):
        External calls:
        - onlyProtectionAdmin(token) (contracts/TreasuryProtectionStrategy.sol#36)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        State variables written after the call(s):
        - protectedAddresses[token].protection[protectedAddress].whitelist[whitelist[i]] = true (contracts/TreasuryProtectionStrategy.sol#38)
Reentrancy in LiquidityProtectionMultipleLimitsStrategy.unpause(address,address) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#85-96):
        External calls:
        - onlyProtectionAdmin(token) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#85)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        State variables written after the call(s):
        - limits[0] = cloneLimit(limits.length - 1,limits) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#91)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#reentrancy-vulnerabilities-2

Reentrancy in LERC20.approve(address,uint256) (contracts/LERC20.sol#205-209):
        External calls:
        - lssAprove(spender,amount) (contracts/LERC20.sol#205)
                - lossless.beforeApprove(_msgSender(),spender,amount) (contracts/LERC20.sol#83)
        Event emitted after the call(s):
        - Approval(owner,spender,amount) (contracts/LERC20.sol#259)
                - _approve(_msgSender(),spender,amount) (contracts/LERC20.sol#207)
Reentrancy in LERC20.decreaseAllowance(address,uint256) (contracts/LERC20.sol#226-232):
        External calls:
        - lssDecreaseAllowance(spender,subtractedValue) (contracts/LERC20.sol#226)
                - lossless.beforeDecreaseAllowance(_msgSender(),spender,subtractedValue) (contracts/LERC20.sol#111)
        Event emitted after the call(s):
        - Approval(owner,spender,amount) (contracts/LERC20.sol#259)
                - _approve(_msgSender(),spender,currentAllowance - subtractedValue) (contracts/LERC20.sol#229)
Reentrancy in LERC20.increaseAllowance(address,uint256) (contracts/LERC20.sol#221-224):
        External calls:
        - lssIncreaseAllowance(spender,addedValue) (contracts/LERC20.sol#221)
                - lossless.beforeIncreaseAllowance(_msgSender(),spender,addedValue) (contracts/LERC20.sol#104)
        Event emitted after the call(s):
        - Approval(owner,spender,amount) (contracts/LERC20.sol#259)
                - _approve(_msgSender(),spender,_allowances[_msgSender()][spender] + addedValue) (contracts/LERC20.sol#222)
Reentrancy in LERC20.transfer(address,uint256) (contracts/LERC20.sol#196-199):
        External calls:
        - lssTransfer(recipient,amount) (contracts/LERC20.sol#196)
                - lossless.beforeTransfer(_msgSender(),recipient,amount) (contracts/LERC20.sol#90)
        Event emitted after the call(s):
        - Transfer(sender,recipient,amount) (contracts/LERC20.sol#243)
                - _transfer(_msgSender(),recipient,amount) (contracts/LERC20.sol#197)
Reentrancy in LERC20.transferFrom(address,address,uint256) (contracts/LERC20.sol#211-219):
        External calls:
        - lssTransferFrom(sender,recipient,amount) (contracts/LERC20.sol#211)
                - lossless.beforeTransferFrom(_msgSender(),sender,recipient,amount) (contracts/LERC20.sol#97)
        Event emitted after the call(s):
        - Approval(owner,spender,amount) (contracts/LERC20.sol#259)
                - _approve(sender,_msgSender(),currentAllowance - amount) (contracts/LERC20.sol#216)
        - Transfer(sender,recipient,amount) (contracts/LERC20.sol#243)
                - _transfer(sender,recipient,amount) (contracts/LERC20.sol#212)
Reentrancy in LosslessGuardian.verifyAddress(address,address,bool) (contracts/LosslessGuardian.sol#78-81):
        External calls:
        - onlyLosslessAdmin() (contracts/LosslessGuardian.sol#78)
                - require(bool,string)(msg.sender == lossless.admin(),LOSSLESS: Not lossless admin) (contracts/LosslessGuardian.sol#41)
        Event emitted after the call(s):
        - AddressVerified(token,verifiedAddress,value) (contracts/LosslessGuardian.sol#80)
Reentrancy in LosslessGuardian.verifyStrategies(address[],bool) (contracts/LosslessGuardian.sol#64-69):
        External calls:
        - onlyLosslessAdmin() (contracts/LosslessGuardian.sol#64)
                - require(bool,string)(msg.sender == lossless.admin(),LOSSLESS: Not lossless admin) (contracts/LosslessGuardian.sol#41)
        Event emitted after the call(s):
        - StrategyVerified(strategies[i],value) (contracts/LosslessGuardian.sol#67)
Reentrancy in LosslessGuardian.verifyToken(address,bool) (contracts/LosslessGuardian.sol#72-75):
        External calls:
        - onlyLosslessAdmin() (contracts/LosslessGuardian.sol#72)
                - require(bool,string)(msg.sender == lossless.admin(),LOSSLESS: Not lossless admin) (contracts/LosslessGuardian.sol#41)
        Event emitted after the call(s):
        - TokenVerified(token,value) (contracts/LosslessGuardian.sol#74)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#reentrancy-vulnerabilities-3

Reentrancy in LiquidityProtectionMultipleLimitsStrategy.pause(address,address) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#67-81):
        External calls:
        - onlyProtectionAdmin(token) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#67)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        Event emitted after the call(s):
        - Paused(token,protectedAddress) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#80)
Reentrancy in LiquidityProtectionSingleLimitStrategy.pause(address,address) (contracts/LiquidityProtectionSingleLimitStrategy.sol#74-80):
        External calls:
        - onlyProtectionAdmin(token) (contracts/LiquidityProtectionSingleLimitStrategy.sol#74)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        Event emitted after the call(s):
        - Paused(token,protectedAddress) (contracts/LiquidityProtectionSingleLimitStrategy.sol#79)
Reentrancy in TreasuryProtectionStrategy.removeProtectedAddresses(address,address[]) (contracts/TreasuryProtectionStrategy.sol#45-51):
        External calls:
        - onlyProtectionAdmin(token) (contracts/TreasuryProtectionStrategy.sol#45)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        Event emitted after the call(s):
        - RemovedWhitelistAddresses(token,addressesToRemove) (contracts/TreasuryProtectionStrategy.sol#50)
Reentrancy in StrategyBase.setGuardian(Guardian) (contracts/StrategyBase.sol#43-47):
        External calls:
        - require(bool,string)(msg.sender == controller.admin(),LOSSLESS: Not lossless admin) (contracts/StrategyBase.sol#44)
        Event emitted after the call(s):
        - GuardianSet(address(newGuardian)) (contracts/StrategyBase.sol#46)
Reentrancy in TreasuryProtectionStrategy.setProtectedAddress(address,address,address[]) (contracts/TreasuryProtectionStrategy.sol#36-42):
        External calls:
        - onlyProtectionAdmin(token) (contracts/TreasuryProtectionStrategy.sol#36)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        Event emitted after the call(s):
        - WhitelistAddresses(token,protectedAddress,whitelist) (contracts/TreasuryProtectionStrategy.sol#40)
Reentrancy in LiquidityProtectionMultipleLimitsStrategy.unpause(address,address) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#85-96):
        External calls:
        - onlyProtectionAdmin(token) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#85)
                - require(bool,string)(msg.sender == guardian.protectionAdmin(token),LOSSLESS: Not protection admin) (contracts/StrategyBase.sol#36)
        Event emitted after the call(s):
        - Unpaused(token,protectedAddress) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#95)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#reentrancy-vulnerabilities-3

LERC20.executeLosslessTurnOff() (contracts/LERC20.sol#160-166) uses timestamp for comparisons
        Dangerous comparisons:
        - require(bool,string)(losslessTurnOffTimestamp <= block.timestamp,LERC20: Time lock in progress) (contracts/LERC20.sol#162)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#block-timestamp

LiquidityProtectionMultipleLimitsStrategy.isTransferAllowed(address,address,address,uint256) (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#101-120) uses timestamp for comparisons
        Dangerous comparisons:
        - limit.lastCheckpointTime + limit.periodInSeconds > block.timestamp (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#109)
LiquidityProtectionSingleLimitStrategy.isTransferAllowed(address,address,address,uint256) (contracts/LiquidityProtectionSingleLimitStrategy.sol#85-100) uses timestamp for comparisons
        Dangerous comparisons:
        - limit.lastCheckpointTime + limit.periodInSeconds > block.timestamp (contracts/LiquidityProtectionSingleLimitStrategy.sol#90)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#block-timestamp

Context._msgData() (contracts/LERC20.sol#9-12) is never used and should be removed
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#dead-code

Pragma version^0.8.0 (contracts/LERC20.sol#2) necessitates a version too recent to be trusted. Consider deploying with 0.6.12/0.7.6
Pragma version^0.8.0 (contracts/LERC20Mock.sol#2) necessitates a version too recent to be trusted. Consider deploying with 0.6.12/0.7.6
Pragma version^0.8.0 (contracts/LosslessGuardian.sol#2) necessitates a version too recent to be trusted. Consider deploying with 0.6.12/0.7.6
solc-0.8.9 is not recommended for deployment
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#incorrect-versions-of-solidity

Pragma version^0.8.0 (contracts/LiquidityProtectionMultipleLimitsStrategy.sol#2) necessitates a version too recent to be trusted. Consider deploying with 0.6.12/0.7.6     
Pragma version^0.8.0 (contracts/LiquidityProtectionSingleLimitStrategy.sol#2) necessitates a version too recent to be trusted. Consider deploying with 0.6.12/0.7.6        
Pragma version^0.8.0 (contracts/StrategyBase.sol#2) necessitates a version too recent to be trusted. Consider deploying with 0.6.12/0.7.6
Pragma version^0.8.0 (contracts/TreasuryProtectionStrategy.sol#2) necessitates a version too recent to be trusted. Consider deploying with 0.6.12/0.7.6
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#incorrect-versions-of-solidity

Pragma version^0.8.0 (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol#4) necessitates a version too recent to be trusted. Consider deploying with 0.6.12/0.7.6
Pragma version^0.8.0 (node_modules/@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol#4) necessitates a version too recent to be trusted. Consider deploying with 0.6.12/0.7.6
Pragma version^0.8.0 (node_modules/@openzeppelin/contracts-upgradeable/utils/ContextUpgradeable.sol#4) necessitates a version too recent to be trusted. Consider deploying with 0.6.12/0.7.6
Pragma version^0.8.0 (contracts/LosslessControllerV1.sol#2) necessitates a version too recent to be trusted. Consider deploying with 0.6.12/0.7.6
Pragma version^0.8.0 (contracts/LosslessControllerV2.sol#2) necessitates a version too recent to be trusted. Consider deploying with 0.6.12/0.7.6
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#incorrect-versions-of-solidity

Function PausableUpgradeable.__Pausable_init() (node_modules/@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol#34-37) is not in mixedCase
Function PausableUpgradeable.__Pausable_init_unchained() (node_modules/@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol#39-41) is not in mixedCase     
Variable PausableUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol#97) is not in mixedCase
Function ContextUpgradeable.__Context_init() (node_modules/@openzeppelin/contracts-upgradeable/utils/ContextUpgradeable.sol#18-20) is not in mixedCase
Function ContextUpgradeable.__Context_init_unchained() (node_modules/@openzeppelin/contracts-upgradeable/utils/ContextUpgradeable.sol#22-23) is not in mixedCase
Variable ContextUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/utils/ContextUpgradeable.sol#31) is not in mixedCase
Parameter LosslessControllerV1.initialize(address,address,address)._admin (contracts/LosslessControllerV1.sol#29) is not in mixedCase
Parameter LosslessControllerV1.initialize(address,address,address)._recoveryAdmin (contracts/LosslessControllerV1.sol#29) is not in mixedCase
Parameter LosslessControllerV1.initialize(address,address,address)._pauseAdmin (contracts/LosslessControllerV1.sol#29) is not in mixedCase
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#conformance-to-solidity-naming-conventions

Redundant expression "this (contracts/LERC20.sol#10)" inContext (contracts/LERC20.sol#4-13)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#redundant-statements

Variable LERC20._totalSupply (contracts/LERC20.sol#48) is too similar to LERC20.constructor(uint256,string,string,address,address,uint256,address).totalSupply_ (contracts/LERC20.sol#69)
Variable LERC20Mock.constructor(uint256,string,string,address,uint256,address,address,address,uint256)._timelockPeriod (contracts/LERC20Mock.sol#16) is too similar to LERC20.constructor(uint256,string,string,address,address,uint256,address).timelockPeriod_ (contracts/LERC20.sol#69)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#variable-names-are-too-similar

PausableUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol#97) is never used in LosslessControllerV1 (contracts/LosslessControllerV1.sol#8-92)
PausableUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol#97) is never used in LosslessControllerV2 (contracts/LosslessControllerV2.sol#12-177)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#unused-state-variable

name() should be declared external:
        - LERC20.name() (contracts/LERC20.sol#176-178)
symbol() should be declared external:
        - LERC20.symbol() (contracts/LERC20.sol#180-182)
decimals() should be declared external:
        - LERC20.decimals() (contracts/LERC20.sol#184-186)
totalSupply() should be declared external:
        - LERC20.totalSupply() (contracts/LERC20.sol#188-190)
transfer(address,uint256) should be declared external:
        - LERC20.transfer(address,uint256) (contracts/LERC20.sol#196-199)
allowance(address,address) should be declared external:
        - LERC20.allowance(address,address) (contracts/LERC20.sol#201-203)
approve(address,uint256) should be declared external:
        - LERC20.approve(address,uint256) (contracts/LERC20.sol#205-209)
transferFrom(address,address,uint256) should be declared external:
        - LERC20.transferFrom(address,address,uint256) (contracts/LERC20.sol#211-219)
increaseAllowance(address,uint256) should be declared external:
        - LERC20.increaseAllowance(address,uint256) (contracts/LERC20.sol#221-224)
decreaseAllowance(address,uint256) should be declared external:
        - LERC20.decreaseAllowance(address,uint256) (contracts/LERC20.sol#226-232)
mint(address,uint256) should be declared external:
        - LERC20Mock.mint(address,uint256) (contracts/LERC20Mock.sol#21-23)
transferInternal(address,address,uint256) should be declared external:
        - LERC20Mock.transferInternal(address,address,uint256) (contracts/LERC20Mock.sol#25-27)
approveInternal(address,address,uint256) should be declared external:
        - LERC20Mock.approveInternal(address,address,uint256) (contracts/LERC20Mock.sol#29-31)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#public-function-that-could-be-declared-external

setProtectedAddress(address,address,address[]) should be declared external:
        - TreasuryProtectionStrategy.setProtectedAddress(address,address,address[]) (contracts/TreasuryProtectionStrategy.sol#36-42)
removeProtectedAddresses(address,address[]) should be declared external:
        - TreasuryProtectionStrategy.removeProtectedAddresses(address,address[]) (contracts/TreasuryProtectionStrategy.sol#45-51)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#public-function-that-could-be-declared-external

initialize(address,address,address) should be declared external:
        - LosslessControllerV1.initialize(address,address,address) (contracts/LosslessControllerV1.sol#29-33)
pause() should be declared external:
        - LosslessControllerV1.pause() (contracts/LosslessControllerV1.sol#37-40)
unpause() should be declared external:
        - LosslessControllerV1.unpause() (contracts/LosslessControllerV1.sol#42-45)
setAdmin(address) should be declared external:
        - LosslessControllerV1.setAdmin(address) (contracts/LosslessControllerV1.sol#47-50)
setRecoveryAdmin(address) should be declared external:
        - LosslessControllerV1.setRecoveryAdmin(address) (contracts/LosslessControllerV1.sol#52-55)
setPauseAdmin(address) should be declared external:
        - LosslessControllerV1.setPauseAdmin(address) (contracts/LosslessControllerV1.sol#57-60)
getVersion() should be declared external:
        - LosslessControllerV1.getVersion() (contracts/LosslessControllerV1.sol#64-66)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#public-function-that-could-be-declared-external
```;
