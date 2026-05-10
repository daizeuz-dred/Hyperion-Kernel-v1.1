<img width="4096" height="2232" alt="Picsart_26-05-10_14-03-57-642" src="https://github.com/user-attachments/assets/52bc240e-62a4-4cb7-8a20-c9d5bd4683f7" />


# Hyperion Kernel v1.1 - "The Quiet Resilience"

### 🛡️ KernelSU & Root Enhancements
* **RKSU v3 Integration:** Updated to the latest RKSU for improved root management and stealth.
* **Multi-Manager Support:** Native compatibility for RKSU, MKSU, Official KernelSU, KowSU, KSUN, WKSU, and WKSU.

### 🚀 Performance & UI Smoothness
* **Multi-Gen LRU (MGLRU) Tuning:** Set `min_ttl` to 1000ms to keep active apps in memory longer, reducing app-reloading `jank.`
* **Memory Management:** Boosted `swappiness` to 120 and adjusted watermarks to prioritize ZRAM, keeping physical RAM free for foreground tasks.
* **Optimized Entropy:** Forced the use of `/dev/urandom` to prevent `read hangs,` resulting in faster app opening speeds.
* **Big.LITTLE Masks:** Properly defined CPU clusters to ensure the scheduler hits the performance cores correctly during heavy loads.

### 🛠️ Stability & Core Refactoring
* **Complete DMA Pool Overhaul:** Backported the full `dmapool` series from upstream. This optimizes how hardware drivers (GPU/Camera) access memory, critical for the 1.1GHz GPU overclock.
* **Reduced Overhead:** Removed redundant `memset` calls and simplified memory freeing logic in the DMA subsystem.
* **Memory Linking:** Enabled block linking across pages to reduce memory fragmentation.

### 🧹 System Cleanliness (Debloat)
* **Hard-Blocked Bloatware:** Implemented kernel-level blocking for various userspace services and trackers to free up CPU cycles.
* **Log Spam Reduction:** Prevented `libperfmgr` from flooding the `logd` socket, saving both battery and storage I/O.

### 🔧 Bug Fixes
* **FS/Exec Fix:** Resolved syntax issues in process execution logic for cleaner syscall handling.
* **Scheduler Safety:** Ensured proper header inclusion for `sched param` tasks.

---

**Recent Changelog (v1.0):** [Hyperion Kernel v1.0 - The Silent Peak](https://github.com/daizeuz-dred/Hyperion-Kernel-V1-Releases#hyperion-kernel-v10--the-silent-peak)

**Maintainer:** D Ξ Ξ Z N U T Z

**Target Device:** Realme 8i / Narzo 50 (spaced)

**Credits:** @HELLINFIX for base sources.

