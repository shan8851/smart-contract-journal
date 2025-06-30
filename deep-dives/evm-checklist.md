# ✅ EVM Opcode Study Checklist

This file tracks a structured progression for learning EVM opcodes and internals using [evm.codes](https://www.evm.codes/) as a primary reference.

---

## 🟢 Beginner: Fundamentals & Variable Access

| Topic | Related Opcodes | What to Look For |
|-------|------------------|------------------|
| Stack Basics | `PUSH`, `POP`, `DUP`, `SWAP` | How values are moved around on the stack |
| Global Variables | `CALLER`, `CALLVALUE`, `GAS`, `GASPRICE`, `TIMESTAMP` | How `msg.sender`, `msg.value`, etc. are accessed |
| Arithmetic | `ADD`, `SUB`, `MUL`, `DIV`, `MOD` | Basic math operations and gas costs |
| Comparison | `EQ`, `LT`, `GT`, `ISZERO` | How conditionals (`require`) work |
| Memory | `MSTORE`, `MLOAD`, `MSIZE` | Working with memory — used for returns and internal variables |
| Control Flow | `JUMP`, `JUMPI`, `JUMPDEST` | How function dispatch and branching logic works |
| Return Data | `RETURN`, `REVERT`, `STOP` | Exiting functions cleanly or reverting with/without data |

---

## 🟡 Intermediate: Data Layout & Contract Communication

| Topic | Related Opcodes | Use Cases |
|-------|------------------|-----------|
| Persistent Storage | `SSTORE`, `SLOAD` | How Solidity handles state variable persistence |
| Function Selector Logic | `CALLDATALOAD`, `CALLDATACOPY`, `CALLDATASIZE` | How the correct function is selected from calldata |
| Contract Calls | `CALL`, `DELEGATECALL`, `STATICCALL`, `CALLCODE` | Composability, upgradeability, and internal call patterns |
| Logs & Events | `LOG0` → `LOG4` | How events are emitted and indexed |
| Keccak Hashing | `SHA3` | Used for mappings, storage slots, and CREATE2 |
| Error Handling | `REVERT`, `INVALID`, `RETURN` | Learn the difference between clean reverts, invalid opcodes, and halting |
| External Code Access | `EXTCODESIZE`, `EXTCODECOPY`, `EXTCODEHASH` | Used to verify if an address is a contract, or introspect it |

---

## 🔴 Advanced: Proxy, Gas Optimization, and Creation Logic

| Topic | Related Opcodes | Learn When... |
|-------|------------------|----------------|
| Contract Creation | `CREATE`, `CREATE2` | Learn deterministic deploys and initcode composition |
| Gas Insights | `GAS`, `GASLIMIT`, `BASEFEE` | Used in advanced fee logic or dynamic gas consumption |
| Self-Destruct | `SELFDESTRUCT` | Understand when and why contracts might remove themselves |
| Delegate Proxies | `DELEGATECALL` + slot management | Critical for upgradable contracts and plugins |
| Code Introspection | `CODESIZE`, `CODECOPY` | Used in minimal proxies, clones, and factory deploys |
| Initcode Crafting | (Manual opcode sequences) | Learn how to build minimal deployable bytecode |
| CREATE2 Predictability | Salt + bytecode hashing | Essential for factories, plugins, and modular deployments |

---

## 🧠 How to Use This Checklist

- Pick 1–2 topics per week
- Use [evm.codes](https://www.evm.codes/) to study the opcode in detail
- Cross-reference with contracts you're reading or writing
- Optionally write notes in `deep-dives/` or daily logs

You can mark off completed sections, and add notes or examples below each section as you go.
