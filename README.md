Munin-Plugins für Sophora
=========
Mit diesen Plugins ist es möglich die Werte von Sophora (Server sowie Webapp) auszulesen. Zudem gibt es Abfragen für den Tomcat.

Benutzung
=========
* Auschecken nach z.B. /usr/share/munin/plugins/custom/
* Links anlegen in /etc/munin/plugins:
```
ln -s /usr/share/munin/plugins/custom/jmx_ /etc/munin/plugins/jmx_sophora_process_memory
ln -s /usr/share/munin/plugins/custom/jmx_ /etc/munin/plugins/jmx_sophora_threads
ln -s /usr/share/munin/plugins/custom/jmx_ /etc/munin/plugins/jmx_sophora_webapp_profiler_durations
ln -s /usr/share/munin/plugins/custom/jmx_ /etc/munin/plugins/jmx_sophora_webapp_profiler_generations
ln -s /usr/share/munin/plugins/custom/jmx_ /etc/munin/plugins/jmx_sophora_webapp_queue

ln -s /usr/share/munin/plugins/custom/jmx_ /etc/munin/plugins/jmx_tomcat_requests
ln -s /usr/share/munin/plugins/custom/jmx_ /etc/munin/plugins/jmx_tomcat_threads
ln -s /usr/share/munin/plugins/custom/jmx_ /etc/munin/plugins/jmx_tomcat_traffic
```
* Konfigurieren in:
```
[jmx_sophora_*]
env.jmxurl service:jmx:rmi://localhost:1198/jndi/rmi://localhost:1199/server
env.jmxuser foo
env.jmxpass bar

[jmx_sophora_webapp_*]
env.jmxurl service:jmx:rmi:///jndi/rmi://localhost:9004/jmxrmi
env.jmxuser foo
env.jmxpass bar

[jmx_tomcat_*]
env.jmxurl service:jmx:rmi:///jndi/rmi://localhost:9004/jmxrmi
env.jmxuser foo
env.jmxpass bar
```
