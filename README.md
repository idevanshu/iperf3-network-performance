<h1>Continuous iperf3 Network Performance Testing</h1>

<h3>Overview</h3>
<strong>This repository features a script for continuous network performance testing using iperf3. The script operates in both normal mode (to measure upload speeds) and reverse mode (to measure download speeds). It runs in an infinite loop with a 10-second pause between tests, providing ongoing monitoring and evaluation of network performance metrics.</strong>

<h3>Use Case Scenario</h3>
<p>This script is useful in scenarios where continuous network performance monitoring is required, such as:</p>
<ul>
    <li>Testing the performance of a new network setup or hardware.</li>
    <li>Monitoring network performance over time to detect fluctuations or issues.</li>
    <li>Validating network configurations and diagnosing performance-related problems.</li>
</ul>

<h3>Prerequisites</h3>
<p>Ensure you have <code>iperf3</code> installed on both the client and server machines. You can install it using:</p>
<pre><code>sudo apt-get install iperf3 -y</code></pre>

<h3>Quick Start</h3>
<ol>
    <li>
        <h3> Creation of bash file
            <pre> <code>nano iperf3_test.sh</code> </pre>
        </h3>
        <pre><code># Define server IP
  SERVER_IP="server_ip_running_iperf3_server"
  # Run the tests in an infinite loop
  while true; do
      echo "Starting iperf3 test in normal mode..."
      sudo iperf3 -c $SERVER_IP
      echo "Normal mode test completed."
      echo "Starting iperf3 test in reverse mode..."
      sudo iperf3 -c $SERVER_IP -R
      echo "Reverse mode test completed."
      echo "Waiting for 10 seconds before the next test..."
      sleep 10 # Wait time between tests
  done
</code></pre>
    </li>
    <li>
        <h3>make the bash file executable </h3>
        <strong><pre><code>sudo chmod +x ./iperf3_test.sh </code></pre></strong>
    </li>
    <li>
        <h3>Run the Script:</h3>
        <p>Execute the script to start continuous testing:</p>
        <pre><code>sudo ./iperf3_test.sh</code></pre>
    </li>
</ol>

<h2>Script Details</h2>
<strong>The script performs the following actions:</strong>
<ul>
    <li>Starts an <code>iperf3</code> Test in normal mode to measure upload speeds.</li>
    <li>Starts an <code>iperf3</code> Test in reverse mode to measure download speeds.</li>
    <li>Waits for 10 seconds before repeating the tests.</li>
</ul>
