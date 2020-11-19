# my_robot

ROSロボット構築のテスト用リポジトリ

---

# Instration

---

- ワークスペースの準備

  ```bash
  $ mkdir -p catkin_ws/src  
  ```

- リポジトリーのクローン

  ```bash
  $ cd catkin_ws/src
  $ git clone https://github.com/DaiGuard/my_robot
  ```

- 依存リポジトリの準備

  ```bash
  $ cd catkin_ws
  $ wstool init src
  $ wstool merge -t src/my_robot/my_robot.rosinstall
  $ wstool update -t src
  ```

- 依存パッケージのインストール

  ```bash
  $ cd catkin_ws
  $ sudo rosdep init
  $ rosdep update
  $ rosdep install --from-paths src --ignore-src -y
  ```

- ワークスペース内をビルドする

  ```bash
  $ cd catkin_ws
  $ catkin build
  ```

# Test

---

- Gazeboを起動する

  ```bash
  $ cd catkin_ws
  $ source devel/setup.bash
  $ roslaunch my_robot_gazebo spawn_my_robot.launch
  ```

- ハンド操作用のGUIを起動する

  ```bash
  $ rosrun rqt_joint_trajectory_controller rqt_joint_trajectory_controller 
  ```

![](https://user-images.githubusercontent.com/26181834/99646773-410f9a00-2a94-11eb-89a9-60f12a2ce759.gif)