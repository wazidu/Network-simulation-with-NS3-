				
</p><p><br />
</p>
<div id="toc" class="toc"><div id="toctitle"><h2>Contents</h2></div>
<ul>
<li class="toclevel-1 tocsection-1"><a href="#Simple_client-server_communication_.28NS-3_Warmup.29"><span class="tocnumber">1</span> <span class="toctext">Simple client-server communication (NS-3 Warmup)</span></a></li>
<li class="toclevel-1 tocsection-2"><a href="#TCP_variants"><span class="tocnumber">2</span> <span class="toctext">TCP variants</span></a></li>
<li class="toclevel-1 tocsection-3"><a href="#TCP_and_router_queues"><span class="tocnumber">3</span> <span class="toctext">TCP and router queues</span></a></li>
<li class="toclevel-1 tocsection-4"><a href="#Routing_.28Optimised_Link_State_Routing.29"><span class="tocnumber">4</span> <span class="toctext">Routing (Optimised Link State Routing)</span></a></li>
<li class="toclevel-1 tocsection-5"><a href="#Wifi_RTS.2FCTS"><span class="tocnumber">5</span> <span class="toctext">Wifi RTS/CTS</span></a></li>
<li class="toclevel-1 tocsection-6"><a href="#Wifi_Channels"><span class="tocnumber">6</span> <span class="toctext">Wifi Channels</span></a></li>
</ul>
</div>

<h2><span class="mw-headline" id="Simple_client-server_communication_.28NS-3_Warmup.29">Simple client-server communication (NS-3 Warmup)</span></h2>
<ul><li> <b>Level</b>: Introductory</li>
<li> <b>Expected learning outcome</b>: NS-3 simulation basics. Basic client server paradigm. Reading pcap traces.</li></ul>
<ul><li> <b>Experiment</b>:
<ol><li> Create a simple topology of two nodes (Node1, Node2) separated by a point-to-point link.</li>
<li> Setup a UdpClient on one Node1 and a UdpServer on Node2. Let it be of a fixed data rate Rate1.</li>
<li> Start the client application, and measure end to end throughput whilst varying the latency of the link.</li>
<li> Now add another client application to Node1 and a server instance to Node2. What do you need to configure to ensure that there is no conflict?</li>
<li> Repeat step 3 with the extra client and server application instances. Show screenshots of pcap traces which indicate that delivery is made to the appropriate server instance.</li></ol></li></ul>
<p><br />
</p>
<h2><span class="mw-headline" id="TCP_variants">TCP variants</span></h2>
<ul><li> <b>Level</b>: Introductory</li>
<li> <b>Expected learning outcome</b>: TCP internals and the difference between each of the variants. NS-3 tracing mechanism.</li></ul>
<ul><li> <b>Experiment</b>:
<ol><li> Create a simple dumbbell topology, two client Node1 and Node2 on the left side of the dumbbell and server nodes Node3 and Node4 on the right side of the dumbbell. Let Node5 and Node6 form the bridge of the dumbbell. Use point to point links.</li>
<li> Install a TCP socket instance on Node1 that will connect to Node3.</li>
<li> Install a UDP socket instance on Node2 that will connect to Node4.</li>
<li> Start the TCP application at time 1s.</li>
<li> Start the UDP application at time 20s at rate Rate1 such that it clogs half the dumbbell bridge's link capacity.</li>
<li> Increase the UDP application's rate at time 30s to rate Rate2 such that it clogs the whole of the dumbbell bridge's capacity.</li>
<li> Use the ns-3 tracing mechanism to record changes in congestion window size of the TCP instance over time. Use gnuplot/matplotlib to visualise plots of cwnd vs time.</li>
<li> Mark points of fast recovery and slow start in the graphs.</li>
<li> Perform the above experiment for TCP variants Tahoe, Reno and New Reno, all of which are available with ns-3.</li></ol></li></ul>
<p><br />
</p>
<h2><span class="mw-headline" id="TCP_and_router_queues">TCP and router queues</span></h2>
<ul><li> <b>Level</b>: Introductory</li>
<li> <b>Expected learning outcome</b>: Queues, packet drops and their effect on congestion window size.</li></ul>
<ul><li> <b>Experiment</b>:
<ol><li> As in previous exercise, Create a simple dumbbell topology, two client Node1 and Node2 on the left side of the dumbbell and server nodes Node3 and Node4 on the right side of the dumbbell. Let Node5 and Node6 form the bridge of the dumbbell. Use point to point links.</li>
<li> Add drop tail queues of size QueueSize5 and QueueSize6 to Node5 and Node6, respectively.</li>
<li> Install a TCP socket instance on Node1 that will connect to Node3.</li>
<li> Install a TCP socket instance on Node2 that will connect to Node3.</li>
<li> Install a TCP socket instance on Node2 that will connect to Node4.</li>
<li> Start Node1--Node3 flow at time 1s, then measure it's throughput. How long does it take to fill link's entire capacity?</li>
<li> Start Node2--Node3 and Node2--Node4 flows at time 15s, measure their throughput.</li>
<li> Measure packet loss and cwnd size, and plot graphs throughput/time, cwnd/time and packet loss/time for each of the flows.</li>
<li> Plot graph throughput/cwnd and packet loss/cwnd for the first flow. Is there an optimal value for cwnd?</li>
<li> Vary QueueSize5 and QueueSize6. Which one has immediate effect on cwnd size of the first flow? Explain why.</li></ol></li></ul>
<p><br />
</p>
<h2><span class="mw-headline" id="Routing_.28Optimised_Link_State_Routing.29">Routing (Optimised Link State Routing)</span></h2>
<ul><li> <b>Level</b>: Introductory</li>
<li> <b>Expected learning outcome</b>: What are MANETs and how they work. OLSR basics. Routing issues associated with MANETs.</li></ul>
<ul><li> <b>Experiment</b>:
<ol><li> Create a wireless mobile ad-hoc network with three nodes Node1, Node2 and Node3. Install the OLSR routing protocol on these nodes.</li>
<li> Place them such that Node1 and Node3 are just out of reach of each other.</li>
<li> Create a UDP client on Node1 and the corresponding server on Node3.</li>
<li> Schedule Node1 to begin sending packets to Node3 at time 1s.</li>
<li> Verify whether Node1 is able to send packets to Node3.</li>
<li> Make Node2 move between Node1 and Node3 such that Node2 is visible to both A and C. This should happen at time 20s. Ensure that Node2 stays in that position for another 15s.</li>
<li> Verify whether Node1 is able to send packets to Node3.</li>
<li> At time 35s, move Node2 out of the region between Node1 and Node3 such that it is out of each other's transmission ranges again.</li>
<li> Verify whether Node1 is able to send packets to Node3.</li>
<li> To verify whether data transmissions occur in the above scenarios, use either the tracing mechanism or a RecvCallback() for Node3's socket.</li>
<li> Plot the number of bytes received versus time at Node3.</li>
<li> Show the pcap traces at Node 2's Wifi interface, and indicate the correlation between Node2's packet reception timeline and Node2's mobility.</li></ol></li></ul>
<p><br />
</p>
<h2><span class="mw-headline" id="Wifi_RTS.2FCTS">Wifi RTS/CTS</span></h2>
<ul><li> <b>Level</b>: Introductory</li>
<li> <b>Expected learning outcome</b>: How 802.11 works with and without RTS/CTS. An insight into why its hard to setup efficient wireless networks.</li></ul>
<ul><li> <b>Experiment</b>:
<ol><li> Setup a 5x5 wireless adhoc network with a grid. You may use examples/wireless/wifi-simple-adhoc-grid.cc as a base.</li>
<li> Install the OLSR routing protocol.</li>
<li> Setup three UDP traffic flows, one along each diagonal and one along the middle (at high rates of transmission).</li>
<li> Setup the ns-3 flow monitor for each of these flows.</li>
<li> Now schedule each of the flows at times 1s, 1.5s, and 2s.</li>
<li> Now using the flow monitor, observe the throughput of each of the UDP flows. Furthermore, use the tracing mechanism to monitor the number of packet collisions/drops at intermediary nodes. Around which nodes are most of the collisions/drops happening?</li>
<li> Now repeat the experiment with RTS/CTS enabled on the wifi devices.</li>
<li> Show the difference in throughput and packet drops if any.</li></ol></li></ul>
<p><br />
</p>
<h2><span class="mw-headline" id="Wifi_Channels">Wifi Channels</span></h2>
<ul><li> <b>Level</b>: IntermediateInstall</li>
<li> <b>Expected learning outcome</b>: How Radio channel models affect transmission. An insight into why its important to correctly model the channel.</li></ul>
<ul><li> <b>Experiment</b>:
<ol><li> Setup a 2-nodes wireless adhoc network. Place the nodes at a fixed distance in a 3d scenario.</li>
<li> Install all the relevant network stacks, up to and including UDP.</li>
<li> Setup a CBR transmission between the nodes, one acting as a server and one as a client. Take the iperf<a rel="nofollow" class="external autonumber" href="http://sourceforge.net/projects/iperf">[1]</a> behaviour as an example.</li>
<li> Setup counters and outputs for packets sent and received.</li>
<li> Schedule the simulation to run for enough time to obtain statistically relevant results (suggestion: analyze some test results and reduce the simulation time accordingly).</li>
<li> Repeat the simulation varying the distance between the nodes from a minimum of 1meter to the point where the nodes can't transmit/receive anymore.</li>
<li> Repeat the above varying the channel models and the transmission/receive parameters like node's position above the ground, transmission power, etc.</li>
<li> Show the differences between the various channel models, and comment them. Identify the channel model that is more appropriate for each case (indoor, outdoor, LoS, NLoS, etc.).</li></ol></li></ul>

<!-- 
NewPP limit report
CPU time usage: 0.011 seconds
Real time usage: 0.044 seconds
Preprocessor visited node count: 23/1000000
Preprocessor generated node count: 28/1000000
Post‐expand include size: 0/2097152 bytes
Template argument size: 0/2097152 bytes
Highest expansion depth: 2/40
Expensive parser function count: 0/100
-->

<!-- Saved in parser cache with key wiki:pcache:idhash:1577-0!*!*!!en!*!* and timestamp 20200911061508 and revision id 7264
 -->
</div>									<div class="printfooter">

	
