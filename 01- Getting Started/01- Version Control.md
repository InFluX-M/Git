# Version Control

## About Version Control System
- Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later.
  - It allows you to revert selected files back to a previous state, revert the entire project back to a previous state, compare changes over time, see who last modified something that might be causing a problem, who introduced an issue and when, and more.

## Types of Version Control Systems
  - Local Version Control Systems (LVS)
  - Centralized Version Control Systems (CVS)
  - Distributed Version Control Systems (DVS)

### Local Version Control Systems
- local VCSs had a simple database that kept all the changes to files under revision control.

![LVS](./Photos/local.png)

### Centralized Version Control Systems
- The next major issue that people encounter is that they need to collaborate with developers on other systems. To deal with this problem, Centralized Version Control Systems (CVCSs) were developed. These systems (such as CVS, Subversion, and Perforce) have a single server that contains all the versioned files, and a number of clients that check out files from that central place.

> The most obvious is the single point of failure that the centralized server represents. If that server goes down for an hour, then during that hour nobody can collaborate at all or save versioned changes to anything they’re working on. If the hard disk the central database is on becomes corrupted, and proper backups haven’t been kept, you lose absolutely everything — the entire history of the project except whatever single snapshots people happen to have on their local machines. Local VCSs suffer from this same problem — whenever you have the entire history of the project in a single place, you risk losing everything.

![CVS](./Photos/centralized.png)

### Distributed Version Control Systems
- This is where Distributed Version Control Systems (DVCSs) step in. In a DVCS (such as **Git**, Mercurial, Bazaar or Darcs), clients don’t just check out the latest snapshot of the files; rather, they fully mirror the repository, including its full history. Thus, if any server dies, and these systems were collaborating via that server, any of the client repositories can be copied back up to the server to restore it. Every clone is really a full backup of all the data.

![DVS](./Photos/distributed.png)
