# Apache Cheat :

Few apache tricks very helpful : 

## __MPM__ Module: 

### /etc/apache2/mods-available/mpm_prefork.conf :



| Name                    | Purpose                                                  | Recommended value |
| ----------------------- | -------------------------------------------------------- | ----------------- |
| **StartServers**        | Max nunber of child server thread innactive.             | ncpu * 2          |
| **MinSpareServers**     | Maximum number of worker threads which are kept spare    | ncpu * 2          |
| **MaxSpareServers**     | Number of child process at startup                       | ncpu * 2          |
| **MaxClients**          | Max number of simultaneous client connections.           | ncpu * 2 + 10     |
| **MaxRequestsPerChild** | Max connections managed by child process                 | 1000              |

