# Palkeoramix decompiler. 

const decimals = 18
const unknown84b0196e = 0xf00000000000000000000000000000000000000000000000000000000000000, 224, 288, chainid, this.address << 96, 0, 352, 8, 0, 0, 1, 0, 0, 0

def storage:
  balanceOf is mapping of uint256 at storage 0
  allowance is mapping of uint256 at storage 1
  totalSupply is uint256 at storage 2
  stor3 is array of struct at storage 3
  stor4 is array of struct at storage 4
  nonces is mapping of uint256 at storage 7
  owner is addr at storage 8

def totalSupply() payable: 
  return totalSupply

def balanceOf(address _owner) payable: 
  require calldata.size - 4 >=ΓÇ▓ 32
  require _owner == _owner
  return balanceOf[addr(_owner)]

def nonces(address _param1) payable: 
  require calldata.size - 4 >=ΓÇ▓ 32
  require _param1 == _param1
  return nonces[addr(_param1)]

def owner() payable: 
  return owner

def allowance(address _owner, address _spender) payable: 
  require calldata.size - 4 >=ΓÇ▓ 64
  require _owner == _owner
  require _spender == _spender
  return allowance[addr(_owner)][addr(_spender)]

#
#  Regular functions
#

def _fallback() payable: # default function
  revert

def renounceOwnership() payable: 
  if owner != caller:
      revert with 0, caller
  owner = 0
  log OwnershipTransferred(
        address previousOwner=owner,
        address newOwner=0)

def transferOwnership(address _newOwner) payable: 
  require calldata.size - 4 >=ΓÇ▓ 32
  require _newOwner == _newOwner
  if owner != caller:
      revert with 0, caller
  require _newOwner
  owner = _newOwner
  log OwnershipTransferred(
        address previousOwner=owner,
        address newOwner=_newOwner)

def burn(uint256 _value) payable: 
  require calldata.size - 4 >=ΓÇ▓ 32
  require caller
  if balanceOf[caller] < _value:
      revert with 0, caller, balanceOf[caller], _value
  balanceOf[caller] -= _value
  totalSupply -= _value
  log Transfer(
        address from=_value,
        address to=caller,
        uint256 tokens=0)

def approve(address _spender, uint256 _value) payable: 
  require calldata.size - 4 >=ΓÇ▓ 64
  require _spender == _spender
  require caller
  require _spender
  allowance[caller][addr(_spender)] = _value
  log Approval(
        address tokenOwner=_value,
        address spender=caller,
        uint256 tokens=_spender)
  return 1

def DOMAIN_SEPARATOR() payable: 
  if this.address != 0xcdcc506f11c7aa95a82dbc2be46b68a8c76b4d56:
      return sha3(0x8b73c3c69bb8fe3d512ecc4cf759cc79239f7b179b0ffacaa9a75d522b39400f, 0xce333a24d070a21c47d536c136aa37242128e224e254c8efcd4a30e66c1ab16c, 0xc89efdaa54c0f20c7adf612882df0950f5a951637e0307cdcb4c672f298b8bc6, chainid, this.address)
  if 56 != chainid:
      return sha3(0x8b73c3c69bb8fe3d512ecc4cf759cc79239f7b179b0ffacaa9a75d522b39400f, 0xce333a24d070a21c47d536c136aa37242128e224e254c8efcd4a30e66c1ab16c, 0xc89efdaa54c0f20c7adf612882df0950f5a951637e0307cdcb4c672f298b8bc6, chainid, this.address)
  return 0x2c5d9009f9d4133f5db92c426d531f6b2b7e962314b8c9531c03a445e89fcb2f

def transfer(address _to, uint256 _value) payable: 
  require calldata.size - 4 >=ΓÇ▓ 64
  require _to == _to
  require caller
  require _to
  if caller:
      if balanceOf[caller] < _value:
          revert with 0, caller, balanceOf[caller], _value
      balanceOf[caller] -= _value
  else:
      if totalSupply > _value + totalSupply:
          revert with 0, 17
      totalSupply += _value
  if _to:
      balanceOf[addr(_to)] += _value
  else:
      totalSupply -= _value
  log Transfer(
        address from=_value,
        address to=caller,
        uint256 tokens=_to)
  return 1

def burnFrom(address _from, uint256 _value) payable: 
  require calldata.size - 4 >=ΓÇ▓ 64
  require _from == _from
  if allowance[addr(_from)][caller] != -1:
      if allowance[addr(_from)][caller] < _value:
          revert with 0, caller, allowance[addr(_from)][caller], _value
      require _from
      require caller
      allowance[addr(_from)][caller] -= _value
  require _from
  if balanceOf[addr(_from)] < _value:
      revert with 0, addr(_from), balanceOf[addr(_from)], _value
  balanceOf[addr(_from)] -= _value
  totalSupply -= _value
  log Transfer(
        address from=_value,
        address to=_from,
        uint256 tokens=0)

def transferFrom(address _from, address _to, uint256 _value) payable: 
  require calldata.size - 4 >=ΓÇ▓ 96
  require _from == _from
  require _to == _to
  if allowance[addr(_from)][caller] != -1:
      if allowance[addr(_from)][caller] < _value:
          revert with 0, caller, allowance[addr(_from)][caller], _value
      require _from
      require caller
      allowance[addr(_from)][caller] -= _value
  require _from
  require _to
  if _from:
      if balanceOf[addr(_from)] < _value:
          revert with 0, addr(_from), balanceOf[addr(_from)], _value
      balanceOf[addr(_from)] -= _value
  else:
      if totalSupply > _value + totalSupply:
          revert with 0, 17
      totalSupply += _value
  if _to:
      balanceOf[addr(_to)] += _value
  else:
      totalSupply -= _value
  log Transfer(
        address from=_value,
        address to=_from,
        uint256 tokens=_to)
  return 1

def unknownd505accf(uint256 _param1, uint256 _param2, uint256 _param3, uint256 _param4, uint256 _param5, uint256 _param6, uint256 _param7) payable: 
  require calldata.size - 4 >=ΓÇ▓ 224
  require _param1 == addr(_param1)
  require _param2 == addr(_param2)
  require _param5 == uint8(_param5)
  if block.timestamp > _param4:
      revert with 0, _param4
  nonces[addr(_param1)]++
  if _param7 > 0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a0:
      revert with 0, _param7
  if this.address != 0xcdcc506f11c7aa95a82dbc2be46b68a8c76b4d56:
      signer = erecover(sha3(6401, sha3(0x8b73c3c69bb8fe3d512ecc4cf759cc79239f7b179b0ffacaa9a75d522b39400f, 0xce333a24d070a21c47d536c136aa37242128e224e254c8efcd4a30e66c1ab16c, 0xc89efdaa54c0f20c7adf612882df0950f5a951637e0307cdcb4c672f298b8bc6, chainid, this.address), sha3(0x6e71edae12b1b97f4d1f60370fef10105fa2faae0126114a169c64845d6126c9, addr(_param1), addr(_param2), _param3, nonces[addr(_param1)], _param4)), _param5 << 248, _param6, _param7) # precompiled
  else:
      if 56 != chainid:
          signer = erecover(sha3(6401, sha3(0x8b73c3c69bb8fe3d512ecc4cf759cc79239f7b179b0ffacaa9a75d522b39400f, 0xce333a24d070a21c47d536c136aa37242128e224e254c8efcd4a30e66c1ab16c, 0xc89efdaa54c0f20c7adf612882df0950f5a951637e0307cdcb4c672f298b8bc6, chainid, this.address), sha3(0x6e71edae12b1b97f4d1f60370fef10105fa2faae0126114a169c64845d6126c9, addr(_param1), addr(_param2), _param3, nonces[addr(_param1)], _param4)), _param5 << 248, _param6, _param7) # precompiled
      else:
          signer = erecover(sha3(6401, 0x2c5d9009f9d4133f5db92c426d531f6b2b7e962314b8c9531c03a445e89fcb2f, sha3(0x6e71edae12b1b97f4d1f60370fef10105fa2faae0126114a169c64845d6126c9, addr(_param1), addr(_param2), _param3, nonces[addr(_param1)], _param4)), _param5 << 248, _param6, _param7) # precompiled
  if not erecover.result:
      revert with ext_call.return_data[0 len return_data.size]
  if not addr(signer):
      revert with 4131778271
  if addr(signer) != addr(_param1):
      revert with 0, addr(signer), addr(_param1)
  require addr(_param1)
  require addr(_param2)
  allowance[addr(_param1)][addr(_param2)] = _param3
  log Approval(
        address tokenOwner=_param3,
        address spender=addr(_param1),
        uint256 tokens=addr(_param2))

def name() payable: 
  if bool(stor3.length):
      if not bool(stor3.length) - (uint255(stor3.length) * 0.5 < 32):
          revert with 0, 34
      if bool(stor3.length):
          if not bool(stor3.length) - (uint255(stor3.length) * 0.5 < 32):
              revert with 0, 34
          if Mask(256, -1, stor3.length):
              if 31 < uint255(stor3.length) * 0.5:
                  mem[128] = uint256(stor3.field_0)
                  idx = 128
                  s = 0
                  while (uint255(stor3.length) * 0.5) + 96 > idx:
                      mem[idx + 32] = stor3[s].field_256
                      idx = idx + 32
                      s = s + 1
                      continue 
                  return Array(len=2 * Mask(256, -1, stor3.length), data=mem[128 len ceil32(uint255(stor3.length) * 0.5)])
              mem[128] = 256 * stor3.length.field_8
      else:
          if not bool(stor3.length) - (stor3.length.field_1 < 32):
              revert with 0, 34
          if stor3.length.field_1:
              if 31 < stor3.length.field_1:
                  mem[128] = uint256(stor3.field_0)
                  idx = 128
                  s = 0
                  while stor3.length.field_1 + 96 > idx:
                      mem[idx + 32] = stor3[s].field_256
                      idx = idx + 32
                      s = s + 1
                      continue 
                  return Array(len=2 * Mask(256, -1, stor3.length), data=mem[128 len ceil32(uint255(stor3.length) * 0.5)])
              mem[128] = 256 * stor3.length.field_8
      mem[ceil32(uint255(stor3.length) * 0.5) + 192 len ceil32(uint255(stor3.length) * 0.5)] = mem[128 len ceil32(uint255(stor3.length) * 0.5)]
      mem[ceil32(uint255(stor3.length) * 0.5) + (uint255(stor3.length) * 0.5) + 192] = 0
      return Array(len=2 * Mask(256, -1, stor3.length), data=mem[128 len ceil32(uint255(stor3.length) * 0.5)], mem[(2 * ceil32(uint255(stor3.length) * 0.5)) + 192 len 2 * ceil32(uint255(stor3.length) * 0.5)]), 
  if not bool(stor3.length) - (stor3.length.field_1 < 32):
      revert with 0, 34
  if bool(stor3.length):
      if not bool(stor3.length) - (uint255(stor3.length) * 0.5 < 32):
          revert with 0, 34
      if Mask(256, -1, stor3.length):
          if 31 < uint255(stor3.length) * 0.5:
              mem[128] = uint256(stor3.field_0)
              idx = 128
              s = 0
              while (uint255(stor3.length) * 0.5) + 96 > idx:
                  mem[idx + 32] = stor3[s].field_256
                  idx = idx + 32
                  s = s + 1
                  continue 
              return Array(len=stor3.length % 128, data=mem[128 len ceil32(stor3.length.field_1)])
          mem[128] = 256 * stor3.length.field_8
  else:
      if not bool(stor3.length) - (stor3.length.field_1 < 32):
          revert with 0, 34
      if stor3.length.field_1:
          if 31 < stor3.length.field_1:
              mem[128] = uint256(stor3.field_0)
              idx = 128
              s = 0
              while stor3.length.field_1 + 96 > idx:
                  mem[idx + 32] = stor3[s].field_256
                  idx = idx + 32
                  s = s + 1
                  continue 
              return Array(len=stor3.length % 128, data=mem[128 len ceil32(stor3.length.field_1)])
          mem[128] = 256 * stor3.length.field_8
  mem[ceil32(stor3.length.field_1) + 192 len ceil32(stor3.length.field_1)] = mem[128 len ceil32(stor3.length.field_1)]
  mem[ceil32(stor3.length.field_1) + stor3.length.field_1 + 192] = 0
  return Array(len=stor3.length % 128, data=mem[128 len ceil32(stor3.length.field_1)], mem[(2 * ceil32(stor3.length.field_1)) + 192 len 2 * ceil32(stor3.length.field_1)]), 

def symbol() payable: 
  if bool(stor4.length):
      if not bool(stor4.length) - (uint255(stor4.length) * 0.5 < 32):
          revert with 0, 34
      if bool(stor4.length):
          if not bool(stor4.length) - (uint255(stor4.length) * 0.5 < 32):
              revert with 0, 34
          if Mask(256, -1, stor4.length):
              if 31 < uint255(stor4.length) * 0.5:
                  mem[128] = uint256(stor4.field_0)
                  idx = 128
                  s = 0
                  while (uint255(stor4.length) * 0.5) + 96 > idx:
                      mem[idx + 32] = stor4[s].field_256
                      idx = idx + 32
                      s = s + 1
                      continue 
                  return Array(len=2 * Mask(256, -1, stor4.length), data=mem[128 len ceil32(uint255(stor4.length) * 0.5)])
              mem[128] = 256 * stor4.length.field_8
      else:
          if not bool(stor4.length) - (stor4.length.field_1 < 32):
              revert with 0, 34
          if stor4.length.field_1:
              if 31 < stor4.length.field_1:
                  mem[128] = uint256(stor4.field_0)
                  idx = 128
                  s = 0
                  while stor4.length.field_1 + 96 > idx:
                      mem[idx + 32] = stor4[s].field_256
                      idx = idx + 32
                      s = s + 1
                      continue 
                  return Array(len=2 * Mask(256, -1, stor4.length), data=mem[128 len ceil32(uint255(stor4.length) * 0.5)])
              mem[128] = 256 * stor4.length.field_8
      mem[ceil32(uint255(stor4.length) * 0.5) + 192 len ceil32(uint255(stor4.length) * 0.5)] = mem[128 len ceil32(uint255(stor4.length) * 0.5)]
      mem[ceil32(uint255(stor4.length) * 0.5) + (uint255(stor4.length) * 0.5) + 192] = 0
      return Array(len=2 * Mask(256, -1, stor4.length), data=mem[128 len ceil32(uint255(stor4.length) * 0.5)], mem[(2 * ceil32(uint255(stor4.length) * 0.5)) + 192 len 2 * ceil32(uint255(stor4.length) * 0.5)]), 
  if not bool(stor4.length) - (stor4.length.field_1 < 32):
      revert with 0, 34
  if bool(stor4.length):
      if not bool(stor4.length) - (uint255(stor4.length) * 0.5 < 32):
          revert with 0, 34
      if Mask(256, -1, stor4.length):
          if 31 < uint255(stor4.length) * 0.5:
              mem[128] = uint256(stor4.field_0)
              idx = 128
              s = 0
              while (uint255(stor4.length) * 0.5) + 96 > idx:
                  mem[idx + 32] = stor4[s].field_256
                  idx = idx + 32
                  s = s + 1
                  continue 
              return Array(len=stor4.length % 128, data=mem[128 len ceil32(stor4.length.field_1)])
          mem[128] = 256 * stor4.length.field_8
  else:
      if not bool(stor4.length) - (stor4.length.field_1 < 32):
          revert with 0, 34
      if stor4.length.field_1:
          if 31 < stor4.length.field_1:
              mem[128] = uint256(stor4.field_0)
              idx = 128
              s = 0
              while stor4.length.field_1 + 96 > idx:
                  mem[idx + 32] = stor4[s].field_256
                  idx = idx + 32
                  s = s + 1
                  continue 
              return Array(len=stor4.length % 128, data=mem[128 len ceil32(stor4.length.field_1)])
          mem[128] = 256 * stor4.length.field_8
  mem[ceil32(stor4.length.field_1) + 192 len ceil32(stor4.length.field_1)] = mem[128 len ceil32(stor4.length.field_1)]
  mem[ceil32(stor4.length.field_1) + stor4.length.field_1 + 192] = 0
  return Array(len=stor4.length % 128, data=mem[128 len ceil32(stor4.length.field_1)], mem[(2 * ceil32(stor4.length.field_1)) + 192 len 2 * ceil32(stor4.length.field_1)]), 


