# AIFX v2 Scripts Directory

**Last Updated**: 2025-11-20
**Cleanup Action**: ULTRATHINK Script Simplification

---

## 📁 Directory Structure

```
scripts/
├── monitoring/     - System monitoring scripts
├── testing/        - Testing scripts
├── maintenance/    - Maintenance scripts
└── archive/        - Archived scripts (old/unused)
```

---

## 🚀 Root Core Scripts (4)

Core scripts retained in the project root:

### 1. **setup.sh** (13K)
**Purpose**: Initialize project setup
```bash
./setup.sh
```
- Install dependencies
- Configure database
- Set environment variables
- Initialize services

### 2. **check_services.sh** (2.6K)
**Purpose**: Check status of all services
```bash
./check_services.sh
```
- ✅ Backend (port 3000)
- ✅ ML Engine (port 8000)
- ✅ Frontend (port 5173)
- ✅ PostgreSQL
- ✅ Redis
- ✅ Discord Bot

### 3. **start-all-services.sh** (4.6K)
**Purpose**: Start all AIFX v2 services
```bash
./start-all-services.sh
```
- Start Backend
- Start ML Engine
- Start Frontend
- Start Discord Bot

### 4. **stop-all-services.sh** (1.9K)
**Purpose**: Stop all AIFX v2 services
```bash
./stop-all-services.sh
```
- Stop all running services
- Clean up processes

---

## 📊 monitoring/ - System Monitoring Scripts

### **system_health_test.sh** (4.8K)
**Purpose**: Full system health check
```bash
./scripts/monitoring/system_health_test.sh
```
- Check all service statuses
- Test API endpoints
- Check database connection
- Generate health report

**Last Updated**: 2025-11-17

---

## 🧪 testing/ - Testing Scripts

### Shell Testing Scripts

#### **quick-test.sh** (6.5K)
**Purpose**: Quick structural test
```bash
./scripts/testing/quick-test.sh
```
- Check project structure
- Verify file existence
- Quick sanity check

#### **test-api.sh** (6.2K)
**Purpose**: API endpoint test
```bash
./scripts/testing/test-api.sh
```
- Test Backend API
- Test ML Engine API
- Verify response format

#### **test_e2e_ml.sh** (1.2K)
**Purpose**: ML engine end-to-end test
```bash
./scripts/testing/test_e2e_ml.sh
```
- Test ML prediction endpoint
- Verify model response

---

### Node.js Testing Scripts

#### **test_discord_integration.js** (4.4K)
**Purpose**: Discord Bot integration test
```bash
node scripts/testing/test_discord_integration.js
```
- Test Discord Bot connection
- Test command functionality
- Verify notification system

#### **test_full_system_diagnosis.js** (14K)
**Purpose**: Full system diagnosis (Most comprehensive)
```bash
node scripts/testing/test_full_system_diagnosis.js
```
- Full system check
- All services diagnosis
- Generate detailed report
- **Recommended for full system verification**

#### **test_market_data_collector.js** (5.4K)
**Purpose**: Market data collection test
```bash
node scripts/testing/test_market_data_collector.js
```
- Test market data collection
- Verify database writes
- Check data integrity

#### **test_signal_end_to_end.js** (3.7K)
**Purpose**: Trading signal end-to-end test
```bash
node scripts/testing/test_signal_end_to_end.js
```
- Test signal generation flow
- From data collection to signal output
- End-to-end verification

#### **test_signal_monitoring.js** (4.6K)
**Purpose**: Signal monitoring service test
```bash
node scripts/testing/test_signal_monitoring.js
```
- Test signal monitoring logic
- Verify reversal detection
- Check notification triggers

---

## 🔧 maintenance/ - Maintenance Scripts

### **verify-system.sh** (7.9K)
**Purpose**: System verification and diagnosis
```bash
./scripts/maintenance/verify-system.sh
```
- Verify system configuration
- Check dependencies
- Diagnose common issues
- Generate fix suggestions

**Last Updated**: 2025-10-27

---

## 📦 archive/ - Archived Scripts

Old or unused scripts (for reference only):

### **check-services.sh** (2.4K)
- Old version service check script
- Replaced by `check_services.sh`
- Last Updated: 2025-10-22

### **start-services.sh** (915B)
- Simplified service start script
- Replaced by `start-all-services.sh`

### **start_frontend.sh** (1.6K)
- Script to start only Frontend
- Limited use, archived

### **test-all-apis.sh** (1.2K)
- Simplified API test
- Replaced by `test-api.sh`

---

## 🎯 Usage Recommendations

### Daily Use
```bash
# Check service status
./check_services.sh

# Start all services
./start-all-services.sh

# Stop all services
./stop-all-services.sh
```

### Testing and Verification
```bash
# Quick test
./scripts/testing/quick-test.sh

# Full system diagnosis (Recommended)
node scripts/testing/test_full_system_diagnosis.js

# API test
./scripts/testing/test-api.sh
```

### System Monitoring
```bash
# Health check
./scripts/monitoring/system_health_test.sh

# System verification
./scripts/maintenance/verify-system.sh
```

---

## 📊 Script Statistics

| Category | Count | Location |
|------|------|------|
| **Core Scripts** | 4 | Root |
| **Monitoring** | 1 | scripts/monitoring/ |
| **Testing** | 8 | scripts/testing/ |
| **Maintenance** | 1 | scripts/maintenance/ |
| **Archive** | 4 | scripts/archive/ |
| **Total** | 18 |  |

---

## 🔄 Script Maintenance Principles

### New Script Rules
- **Core Scripts** (Root): Only keep the 4 most used ones
- **Monitoring Scripts** → `scripts/monitoring/`
- **Testing Scripts** → `scripts/testing/`
- **Maintenance Scripts** → `scripts/maintenance/`
- **Old/Unused** → `scripts/archive/`

### Naming Convention
- Use lowercase and underscores: `script_name.sh`
- Or use dashes: `script-name.sh`
- Maintain consistency

### Documentation Requirements
Each script should contain:
- Usage description
- Usage example
- Update date
- Dependency explanation

---

## 📝 Change History

### 2025-11-20 - ULTRATHINK Script Simplification
- From 18 root scripts → 4 core scripts
- Created scripts/ category directories
- Moved 14 scripts to subdirectories
- Established complete documentation

**Reduced**: 78% root clutter
**Improved**: 100% script categorization

---

**Cleanup Completed**: 2025-11-20
**Method**: ULTRATHINK Deep Analysis
**Effect**: Clear root directory, distinct script categorization
