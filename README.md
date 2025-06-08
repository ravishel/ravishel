- 👋 Hi, I’m @ravishel
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
ravishel/ravishel is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

## Setting Up Pengym in Simulation Mode on Google Colab

The following steps outline how to install and run **Pengym** in simulation mode using Google Colab:

1. Open [Google Colab](https://colab.research.google.com/) and start a new notebook.
2. Install the environment along with common dependencies:
   ```python
   # Install Pengym and dependencies
   !pip install pengym gymnasium pybullet
   ```
   Adjust the packages as needed if your environment requires additional libraries.
3. Import and create the environment in simulation mode, then run a short test to verify everything is working:
   ```python
   import pengym

   env = pengym.make('Pen-v0', mode='sim')  # adjust parameters to match your environment
   obs, info = env.reset()

   for _ in range(10):  # sample a few steps
       action = env.action_space.sample()
       obs, reward, terminated, truncated, info = env.step(action)
       if terminated or truncated:
           obs, info = env.reset()

   env.close()
   print("Environment ran successfully")
   ```
4. After verifying the setup, you can begin experimenting with reinforcement learning algorithms or data collection.

