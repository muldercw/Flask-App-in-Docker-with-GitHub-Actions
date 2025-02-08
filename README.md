<h1>🚀 Flask App in Docker with GitHub Actions</h1>

<p>This repository contains a <strong>simple Flask web application</strong> that runs inside a <strong>Docker container</strong>. A <strong>GitHub Actions workflow</strong> is included to automatically:</p>

<ul>
  <li>✅ Build the Docker container</li>
  <li>✅ Run the container</li>
  <li>✅ Test if it responds correctly</li>
  <li>✅ Stop and remove the container after testing</li>
</ul>

<hr>

<h2>📂 Project Structure</h2>

<pre>
.
├── .github/workflows/docker-flask.yaml  # GitHub Actions workflow
└── app/                                 # Flask app (created dynamically in CI)
</pre>

<hr>

<h2>🛠️ How It Works</h2>

<p>The <strong>GitHub Actions workflow</strong> performs the following:</p>

<ol>
  <li><strong>Creates a simple Flask app dynamically</strong> (app.py).</li>
  <li><strong>Creates a Dockerfile dynamically.</strong></li>
  <li><strong>Builds the Docker container</strong> (flask-app).</li>
  <li><strong>Runs the container</strong> on port <code>5000</code>.</li>
  <li><strong>Tests the app’s response</strong> using <code>curl</code>:</li>
  <pre>
  Expected Output:
  "Hello, Flask is running in a container!"
  </pre>
  <li><strong>Stops and removes</strong> the container after testing.</li>
</ol>

<hr>

<h2>🚀 Running the Workflow</h2>

<p>This workflow <strong>automatically triggers</strong> on <strong>pushes to the main branch</strong>.</p>

<h3>Manual Trigger:</h3>
<ol>
  <li>Go to your repository on GitHub.</li>
  <li>Click on the <strong>"Actions"</strong> tab.</li>
  <li>Select <strong>"Build and Test Flask in Docker"</strong> workflow.</li>
  <li>Click <strong>"Run workflow"</strong>.</li>
</ol>

<hr>

<h2>✅ How to Verify the Workflow</h2>

<p>After the workflow runs, check the <strong>GitHub Actions logs:</strong></p>
<ol>
  <li>Go to the "<strong>Actions</strong>" tab in your GitHub repository.</li>
  <li>Select the latest workflow run.</li>
  <li>Check the logs to see:
    <ul>
      <li>✅ <strong>Container build success</strong></li>
      <li>✅ <strong>Flask app response test success</strong></li>
      <li>✅ <strong>Container stopped & removed successfully</strong></li>
    </ul>
  </li>
</ol>

<hr>

<h2>🐳 Running Locally (Optional)</h2>

<p>If you want to run this locally, follow these steps:</p>

<h3>1️⃣ Clone the Repository</h3>
<pre>
git clone https://github.com/muldercw/Flask-App-in-Docker-with-GitHub-Actions.git
cd YOUR-REPO
</pre>

<h3>2️⃣ Build the Docker Image</h3>
<pre>
docker build -t flask-app .
</pre>

<h3>3️⃣ Run the Container</h3>
<pre>
docker run -d -p 5000:5000 --name flask-container flask-app
</pre>

<h3>4️⃣ Test the App</h3>
<pre>
curl http://localhost:5000
# Expected output: "Hello, Flask is running in a container!"
</pre>

<h3>5️⃣ Stop and Remove the Container</h3>
<pre>
docker stop flask-container
docker rm flask-container
</pre>

<hr>

<h2>🛠️ Future Improvements</h2>

<ul>
  <li>🔹 Push the container to Docker Hub or GitHub Container Registry (GHCR).</li>
  <li>🔹 Run additional integration tests.</li>
  <li>🔹 Deploy to a production Kubernetes cluster or cloud service.</li>
</ul>

<hr>

<h2>📜 License</h2>
<p>This project is open-source under the <strong>MIT License</strong>.</p>

