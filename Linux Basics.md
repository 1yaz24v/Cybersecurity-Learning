<h1>Introduction to Linux and Linux Security</h1>

<ol>
  <li>
    <strong>Overview of Linux</strong>
    <p>Linux is a powerfull and felxible opearting system that's built on something called the Linux Kernel, which you can think of as the "brain" behind the scenes. The kernel controls how the computer's hardware works together, managing things like memory, the CPU, and other device, making sure everything runs smoothly and efficiently.</p>
    <p>However, the kernel by itselft isn't a complete operating system. To make it usable to everyday tasks, it needs a set of tools, program, and utilities. A group of software packages and tools known as Linux distributions are coupled with the Linux kernel to provide a complete and working system.</p>
    <p>These distributions come in various forms, each tailored for different needs—from personal use to servers and cybersecurity. Together, they make Linux a flexible, secure, and efficient platform for a wide range of computing tasks.</p>
  </li>

  <li>
    <strong>Core Linux Concepts</strong>

    <ol>
      <li>
        <strong>File System Hierarchy</strong>
        <p>Linux organizes files in a tree-like structure starting from the root directory /. Each folder has a specific purpose:</p>
        <ul>
          <li>/bin – Contains essential command-line programs (like ls, cp, mv) needed for basic system operations.</li>
          <li>/etc – Stores system-wide configuration files for services and applications.</li>
          <li>/home – Contains personal directories for all regular users (e.g., /home/anuj).</li>
          <li>/var – Holds variable data such as system logs, mail spools, and temporary files.</li>
          <li>/root – The home directory of the root (superuser) account.</li>
          <li>/dev, /proc, /sys – Special virtual directories:
            <ul>
              <li>/dev: Access to hardware devices as files.</li>
              <li>/proc: Real-time system and process information.</li>
              <li>/sys: Interfaces to kernel settings and hardware info.</li>
            </ul>
          </li>
        </ul>
        <p>This structure keeps Linux systems organized, secure, and efficient to manage.</p>
      </li>

      <li>
        <strong>Command-Line Interface (CLI)</strong>
        <p>The CLI is a core tool in Linux system administration, allowing users to interact with the system through text-based commands. Key functions include:</p>
        <ul>
          <li>Navigation: ls (list files), cd (change directory), pwd (show current path)</li>
          <li>File handling: mkdir (create folder), touch (create file), rm (remove file/folder)</li>
          <li>Permissions: chmod (change file permissions), chown (change ownership)</li>
          <li>Privileges: sudo lets users run commands with administrative rights</li>
        </ul>
        <p>Using the CLI provides more control, flexibility, and efficiency compared to graphical interfaces.</p>
      </li>

      <li>
        <strong>Package Management</strong>
        <p>Linux uses package managers to install, update, and remove software. These tools also handle software dependencies, helping maintain system stability.</p>
        <ul>
          <li>Debian/Ubuntu systems use: apt</li>
          <li>Red Hat/CentOS systems use: yum or dnf</li>
        </ul>
        <p>Effective package management is essential for keeping the system secure, up-to-date, and functioning correctly.</p>
      </li>
    </ol>
  </li>
</ol>

<h1>Introduction to Linux Security</h1>

<p>Linux has become a go-to choice for servers, development environments, and cybersecurity tasks, thanks to its reliability, performance, and open-source flexibility. The security features of Linux are deeply integrated into its design, relying on permissions, user roles, and a variety of security tools to keep systems safe. In this section, we’ll dive into the key elements and best practices that play a vital role in securing Linux systems.</p>

<ol>
  <li>
    <strong>User and Permision Management</strong>
    <ul>
      <li>Each file or directory is assigned three sets of permissions: owner, group, and others, using read (r), write (w), and execute (x) flags.</li>
      <li>System integrity is maintained by limiting root (superuser) access. Tools like sudo allow users to execute administrative tasks without logging in as root.</li>
      <li>User activity can be monitored via logs (e.g., /var/log/auth.log) to detect unauthorized access.</li>
    </ul>
  </li>

  <li>
    <strong>File and System Integrity</strong>
    <p>File and system integrity means making sure that important files and system settings are not changed, damaged, or tampered with—either by mistake or by malicious users. Linux protects system integrity in the following ways:</p>

    <ol>
      <li>
        <strong>File Permissions</strong>
        <ul>
          <li>Every file and folder has permissions that control who can read, write, or execute it.</li>
          <li>This helps prevent unauthorized users or programs from changing system files.</li>
          <li>Example: Only the root user or someone with sudo access can change system configuration files.</li>
        </ul>
      </li>

      <li>
        <strong>User Roles</strong>
        <ul>
          <li>Linux separates regular users from the root user (the superuser with full control).</li>
          <li>By limiting root access, the system reduces the risk of accidental or harmful changes.</li>
        </ul>
      </li>

      <li>
        <strong>Mandatory Access Control (MAC)</strong>
        <ul>
          <li>Tools like AppArmor and SELinux add an extra layer of security.</li>
          <li>They control what each application is allowed to do—like which files it can access or modify.</li>
          <li>Even if a program is compromised, MAC systems can stop it from doing damage.</li>
        </ul>
      </li>

      <li>
        <strong>File Integrity Monitoring Tools</strong>
        <ul>
          <li>Tools like AIDE (Advanced Intrusion Detection Environment) or Tripwire can take a snapshot of important files.</li>
          <li>They regularly check if any files have been changed, added, or deleted.</li>
          <li>If something suspicious happens, the system can alert the administrator.</li>
        </ul>
      </li>

      <li>
        <strong>Audit Logs</strong>
        <ul>
          <li>Linux can record system events (like who accessed which file) using audit logs.</li>
          <li>These logs help track any unusual behavior or unauthorized access attempts.</li>
        </ul>
      </li>
    </ol>
  </li>

  <li>
    <strong>Network and Firewall Security</strong>
    <p>A crucial component of protecting any Linux system is network security, particularly those that are online or run in multi-user settings. Linux offers strong configurations and tools to help defend against potential network-based attacks, malicious traffic, and unauthorized access. Administrators can efficiently manage and protect the system's network by utilizing intrusion prevention tools, firewalls, secure remote access protocols, and system logging. Linux provides a solid basis for preserving network security when paired with consistent updates and appropriate service management.</p>

    <ul>
      <li><strong>Firewalls:</strong>
        <ul>
          <li>Linux uses tools like iptables, nftables, and ufw to control network traffic.</li>
          <li>These tools allow or block connections based on defined rules, protecting against unauthorized access.</li>
        </ul>
      </li>

      <li><strong>SSH (Secure Shell):</strong>
        <ul>
          <li>Used for secure remote access.</li>
          <li>Best practices include:
            <ul>
              <li>Disabling root login.</li>
              <li>Using SSH keys instead of passwords.</li>
              <li>Changing the default SSH port.</li>
            </ul>
          </li>
        </ul>
      </li>

      <li><strong>Intrusion Prevention Tools:</strong>
        <ul>
          <li>Tools like Fail2Ban monitor login attempts and block IPs that show suspicious behavior (e.g., brute-force attacks).</li>
        </ul>
      </li>

      <li><strong>System Logs:</strong>
        <ul>
          <li>Logs stored in /var/log/ help monitor network activity.</li>
          <li>Important logs include auth.log (login attempts) and syslog/messages (general system events).</li>
        </ul>
      </li>

      <li><strong>Regular Updates:</strong>
        <ul>
          <li>Keeping the system and software up to date helps fix known vulnerabilities and enhances network security.</li>
        </ul>
      </li>

      <li><strong>Minimal Service Exposure:</strong>
        <ul>
          <li>Only necessary services and open ports should be enabled to reduce the attack surface.</li>
        </ul>
      </li>
    </ul>
  </li>

  <li>
    <strong>Software and Update Management</strong>
    <p>Maintaining current versions of software is very important for both the security and stability of a Linux system. The majority of Linux based OSes leverage package managers like apt, yum and dnf to install, update and remove software. These tools ensure that software is sourced from trustworthy origins and all dependencies are kept under control. Frequent new updates help patch known holes, minimizes the need to use backdoors, and improves performance. It is also a good policy for system administrators to periodically check for updates and apply them promptly, especially on servers or systems connected to internet.</p>

    <ul>
      <li>Use apt (Debian/Ubuntu) or yum/dnf (Red Hat/CentOS) for managing packages.</li>
      <li>Only install software from trusted and official repositories.</li>
      <li>Regularly apply system and security updates.</li>
      <li>Automate updates in critical environments where appropriate.</li>
    </ul>
  </li>

  <li>
    <strong>Logging and Monitoring</strong>
    <p>Linux systems keep detailed records of activities and events, which play a crucial role in security checks and problem-solving. These records are kept in the /var/log/ folder and contain info about system operations, user logins, errors, and service activity. Important logs such as auth.log (for authentication), syslog or messages (for system events), and dmesg (for kernel messages) help spot unauthorized access failed login tries, or odd system behavior. Tools like Logwatch, Syslog, and journalctl (for systemd-based systems) let admins look at log data well. Keeping an eye on logs helps find security problems and gives insights into how healthy the system is.</p>

    <ul>
      <li>Logs are stored in /var/log/ (e.g., auth.log, syslog, dmesg).</li>
      <li>Use journalctl for viewing logs on systemd systems.</li>
      <li>Monitor logs for failed login attempts, system errors, and unusual activity.</li>
      <li>Tools like Logwatch or logrotate help automate log analysis and management.</li>
    </ul>
  </li>
</ol>
