```python
<sdf version='1.7'>
  <model name='octorotor_coaxial'>
    <link name='base_link'>
      <inertial>
        <pose>0 0 0 0 0 0</pose>
        <mass>2.5</mass>
        <inertia>
          <ixx>0.029125</ixx>
          <ixy>0</ixy>
          <ixz>0</ixz>
          <iyy>0.029125</iyy>
          <iyz>0</iyz>
          <izz>0.055225</izz>
        </inertia>
      </inertial>
      <collision name='base_link_collision'>
        <pose>0 0 0 0 0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/base_link.STL</uri>
          </mesh>
        </geometry>
      </collision>
      <visual name='base_link_visual'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/base_link.STL</uri>
          </mesh>
        </geometry>
      </visual>
    </link>
    
     <visual name="com_marker">
        <pose>0 0 0 0 0 0</pose>
        <geometry><sphere><radius>0.01</radius></sphere></geometry>
        <material><ambient>1 0 0 1</ambient><diffuse>1 0 0 1</diffuse></material>
      </visual>

    <link name='/imu_link'>
      <pose>0 0 0.02 0 0 0</pose>
      <inertial>
        <pose>0 0 0 0 0 0</pose>
        <mass>0.015</mass>
        <inertia>
          <ixx>1e-05</ixx>
          <ixy>0</ixy>
          <ixz>0</ixz>
          <iyy>1e-05</iyy>
          <iyz>0</iyz>
          <izz>1e-05</izz>
        </inertia>
      </inertial>
    </link>
    <joint name='/imu_joint' type='revolute'>
      <child>/imu_link</child>
      <parent>base_link</parent>
      <axis>
        <xyz>1 0 0</xyz>
        <limit>
          <lower>0</lower>
          <upper>0</upper>
          <effort>0</effort>
          <velocity>0</velocity>
        </limit>
        <dynamics>
          <spring_reference>0</spring_reference>
          <spring_stiffness>0</spring_stiffness>
        </dynamics>
        <use_parent_model_frame>1</use_parent_model_frame>
      </axis>
    </joint>
    
    <joint name='prop1' type='revolute'>
      <pose relative_to='base_link'>0.192121 -0.193271 0.02855 0 -0 0</pose>
      <parent>base_link</parent>
      <child>link1</child>
      <axis>
        <xyz>0 0 1</xyz>
        <limit>
          <lower>-1e+16</lower>
          <upper>1e+16</upper>
        </limit>
        <dynamics>
          <spring_reference>0</spring_reference>
          <spring_stiffness>0</spring_stiffness>
        </dynamics>
        <use_parent_model_frame>1</use_parent_model_frame>
      </axis>
    </joint>
    <link name='link1'>
      <pose relative_to='prop1'>0 0 0 0 -0 0</pose>
      <inertial>
        <pose>0 -0 -0.003258 0 -0 0</pose>
        <mass>0.015</mass>
        <inertia>
          <ixx>9.75e-07</ixx>
          <ixy>0</ixy>
          <ixz>0</ixz>
          <iyy>0.000273104</iyy>
          <iyz>0</iyz>
          <izz>0.000274004</izz>
        </inertia>
      </inertial>
      <collision name='link1_collision'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link1.STL</uri>
          </mesh>
        </geometry>
        <surface>
          <contact>
            <ode/>
          </contact>
          <friction>
            <ode/>
          </friction>
        </surface>
      </collision>
      <visual name='link1_visual'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link1.STL</uri>
          </mesh>
        </geometry>
      </visual>
      <gravity>1</gravity>
      <velocity_decay/>
    </link>
    
    <joint name='prop2' type='revolute'>
      <pose relative_to='base_link'>0.192452 0.192939 0.02855 0 -0 0</pose>
      <parent>base_link</parent>
      <child>link2</child>
      <axis>
        <xyz>0 0 1</xyz>
        <limit>
          <lower>-1e+16</lower>
          <upper>1e+16</upper>
        </limit>
        <dynamics>
          <spring_reference>0</spring_reference>
          <spring_stiffness>0</spring_stiffness>
        </dynamics>
        <use_parent_model_frame>1</use_parent_model_frame>
      </axis>
    </joint>
    <link name='link2'>
      <pose relative_to='prop2'>0 0 0 0 -0 0</pose>
      <inertial>
        <pose>0 0 -0.003258 0 -0 0</pose>
        <mass>0.015</mass>
        <inertia>
          <ixx>9.75e-07</ixx>
          <ixy>0</ixy>
          <ixz>0</ixz>
          <iyy>0.000273104</iyy>
          <iyz>0</iyz>
          <izz>0.000274004</izz>
        </inertia>
      </inertial>
      <collision name='link2_collision'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link2.STL</uri>
          </mesh>
        </geometry>
        <surface>
          <contact>
            <ode/>
          </contact>
          <friction>
            <ode/>
          </friction>
        </surface>
      </collision>
      <visual name='link2_visual'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link2.STL</uri>
          </mesh>
        </geometry>
      </visual>
      <gravity>1</gravity>
      <velocity_decay/>
    </link>
    
    <joint name='prop3' type='revolute'>
      <pose relative_to='base_link'>-0.19376 0.19261 0.02855 0 -0 0</pose>
      <parent>base_link</parent>
      <child>link3</child>
      <axis>
        <xyz>0 0 1</xyz>
        <limit>
          <lower>-1e+16</lower>
          <upper>1e+16</upper>
        </limit>
        <dynamics>
          <spring_reference>0</spring_reference>
          <spring_stiffness>0</spring_stiffness>
        </dynamics>
        <use_parent_model_frame>1</use_parent_model_frame>
      </axis>
    </joint>
    <link name='link3'>
      <pose relative_to='prop3'>0 0 0 0 -0 0</pose>
      <inertial>
        <pose>0 0 -0.003258 0 -0 0</pose>
        <mass>0.015</mass>
        <inertia>
          <ixx>9.75e-07</ixx>
          <ixy>0</ixy>
          <ixz>0</ixz>
          <iyy>0.000273104</iyy>
          <iyz>0</iyz>
          <izz>0.000274004</izz>
        </inertia>
      </inertial>
      <collision name='link3_collision'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link3.STL</uri>
          </mesh>
        </geometry>
        <surface>
          <contact>
            <ode/>
          </contact>
          <friction>
            <ode/>
          </friction>
        </surface>
      </collision>
      <visual name='link3_visual'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link3.STL</uri>
          </mesh>
        </geometry>
      </visual>
      <gravity>1</gravity>
      <velocity_decay/>
    </link>
    
    <joint name='prop4' type='revolute'>
      <pose relative_to='base_link'>-0.19343 -0.19294 0.02855 0 -0 0</pose>
      <parent>base_link</parent>
      <child>link4</child>
      <axis>
        <xyz>0 0 1</xyz>
        <limit>
          <lower>-1e+16</lower>
          <upper>1e+16</upper>
        </limit>
        <dynamics>
          <spring_reference>0</spring_reference>
          <spring_stiffness>0</spring_stiffness>
        </dynamics>
        <use_parent_model_frame>1</use_parent_model_frame>
      </axis>
    </joint>
    <link name='link4'>
      <pose relative_to='prop4'>0 0 0 0 -0 0</pose>
      <inertial>
        <pose>0 -0 -0.003258 0 -0 0</pose>
        <mass>0.015</mass>
        <inertia>
          <ixx>9.75e-07</ixx>
          <ixy>0</ixy>
          <ixz>0</ixz>
          <iyy>0.000273104</iyy>
          <iyz>0</iyz>
          <izz>0.000274004</izz>
        </inertia>
      </inertial>
      <collision name='link4_collision'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link4.STL</uri>
          </mesh>
        </geometry>
        <surface>
          <contact>
            <ode/>
          </contact>
          <friction>
            <ode/>
          </friction>
        </surface>
      </collision>
      <visual name='link4_visual'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link4.STL</uri>
          </mesh>
        </geometry>
      </visual>
      <gravity>1</gravity>
      <velocity_decay/>
    </link>
    
    <joint name='prop5' type='revolute'>
      <pose relative_to='base_link'>0.19245 0.19294 -0.06825 0 -0 0</pose>
      <parent>base_link</parent>
      <child>link5</child>
      <axis>
        <xyz>0 0 1</xyz>
        <limit>
          <lower>-1e+16</lower>
          <upper>1e+16</upper>
        </limit>
        <dynamics>
          <spring_reference>0</spring_reference>
          <spring_stiffness>0</spring_stiffness>
        </dynamics>
        <use_parent_model_frame>1</use_parent_model_frame>
      </axis>
    </joint>
    <link name='link5'>
      <pose relative_to='prop5'>0 0 0 0 -0 0</pose>
      <inertial>
        <pose>0 0 0.003258 0 -0 0</pose>
        <mass>0.015</mass>
        <inertia>
          <ixx>9.75e-07</ixx>
          <ixy>0</ixy>
          <ixz>0</ixz>
          <iyy>0.000273104</iyy>
          <iyz>0</iyz>
          <izz>0.000274004</izz>
        </inertia>
      </inertial>
      <collision name='link5_collision'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link5.STL</uri>
          </mesh>
        </geometry>
        <surface>
          <contact>
            <ode/>
          </contact>
          <friction>
            <ode/>
          </friction>
        </surface>
      </collision>
      <visual name='link5_visual'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link5.STL</uri>
          </mesh>
        </geometry>
      </visual>
      <gravity>1</gravity>
      <velocity_decay/>
    </link>
    
    <joint name='prop6' type='revolute'>
      <pose relative_to='base_link'>0.19212 -0.19327 -0.06825 0 -0 0</pose>
      <parent>base_link</parent>
      <child>link6</child>
      <axis>
        <xyz>0 0 1</xyz>
        <limit>
          <lower>-1e+16</lower>
          <upper>1e+16</upper>
        </limit>
        <dynamics>
          <spring_reference>0</spring_reference>
          <spring_stiffness>0</spring_stiffness>
        </dynamics>
        <use_parent_model_frame>1</use_parent_model_frame>
      </axis>
    </joint>
    <link name='link6'>
      <pose relative_to='prop6'>0 0 0 0 -0 0</pose>
      <inertial>
        <pose>0 0 0.003258 0 -0 0</pose>
        <mass>0.015</mass>
        <inertia>
          <ixx>9.75e-07</ixx>
          <ixy>0</ixy>
          <ixz>0</ixz>
          <iyy>0.000273104</iyy>
          <iyz>0</iyz>
          <izz>0.000274004</izz>
        </inertia>
      </inertial>
      <collision name='link6_collision'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link6.STL</uri>
          </mesh>
        </geometry>
        <surface>
          <contact>
            <ode/>
          </contact>
          <friction>
            <ode/>
          </friction>
        </surface>
      </collision>
      <visual name='link6_visual'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link6.STL</uri>
          </mesh>
        </geometry>
      </visual>
      <gravity>1</gravity>
      <velocity_decay/>
    </link>
    
    <joint name='prop7' type='revolute'>
      <pose relative_to='base_link'>-0.19343 -0.19294 -0.06825 0 -0 0</pose>
      <parent>base_link</parent>
      <child>link7</child>
      <axis>
        <xyz>0 0 1</xyz>
        <limit>
          <lower>-1e+16</lower>
          <upper>1e+16</upper>
        </limit>
        <dynamics>
          <spring_reference>0</spring_reference>
          <spring_stiffness>0</spring_stiffness>
        </dynamics>
        <use_parent_model_frame>1</use_parent_model_frame>
      </axis>
    </joint>
    <link name='link7'>
      <pose relative_to='prop7'>0 0 0 0 -0 0</pose>
      <inertial>
        <pose>0 0 0.003258 0 -0 0</pose>
        <mass>0.015</mass>
        <inertia>
          <ixx>9.75e-07</ixx>
          <ixy>0</ixy>
          <ixz>0</ixz>
          <iyy>0.000273104</iyy>
          <iyz>0</iyz>
          <izz>0.000274004</izz>
        </inertia>
      </inertial>
      <collision name='link7_collision'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link7.STL</uri>
          </mesh>
        </geometry>
        <surface>
          <contact>
            <ode/>
          </contact>
          <friction>
            <ode/>
          </friction>
        </surface>
      </collision>
      <visual name='link7_visual'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link7.STL</uri>
          </mesh>
        </geometry>
      </visual>
      <gravity>1</gravity>
      <velocity_decay/>
    </link>
    
    <joint name='prop8' type='revolute'>
      <pose relative_to='base_link'>-0.193758 0.192608 -0.06825 0 -0 0</pose>
      <parent>base_link</parent>
      <child>link8</child>
      <axis>
        <xyz>0 0 1</xyz>
        <limit>
          <lower>-1e+16</lower>
          <upper>1e+16</upper>
        </limit>
        <dynamics>
          <spring_reference>0</spring_reference>
          <spring_stiffness>0</spring_stiffness>
        </dynamics>
        <use_parent_model_frame>1</use_parent_model_frame>
      </axis>
    </joint>
    <link name='link8'>
      <pose relative_to='prop8'>0 0 0 0 -0 0</pose>
      <inertial>
        <pose>0 0 0.003258 0 -0 0</pose>
        <mass>0.015</mass>
        <inertia>
          <ixx>9.75e-07</ixx>
          <ixy>0</ixy>
          <ixz>0</ixz>
          <iyy>0.000273104</iyy>
          <iyz>0</iyz>
          <izz>0.000274004</izz>
        </inertia>
      </inertial>
      <collision name='link8_collision'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link8.STL</uri>
          </mesh>
        </geometry>
        <surface>
          <contact>
            <ode/>
          </contact>
          <friction>
            <ode/>
          </friction>
        </surface>
      </collision>
      <visual name='link8_visual'>
        <pose>0 0 0 0 -0 0</pose>
        <geometry>
          <mesh>
            <scale>1 1 1</scale>
            <uri>model://octorotor_coaxial/meshes/link8.STL</uri>
          </mesh>
        </geometry>
      </visual>
      <gravity>1</gravity>
      <velocity_decay/>
    </link>
    
    <plugin name='rosbag' filename='libgazebo_multirotor_base_plugin.so'>
      <robotNamespace/>
      <linkName>base_link</linkName>
      <rotorVelocitySlowdownSim>10</rotorVelocitySlowdownSim>
    </plugin>
    
    <plugin name='front_right_motor_model' filename='libgazebo_motor_model.so'>
      <robotNamespace/>
      <jointName>prop1</jointName>
      <linkName>link1</linkName>
      <turningDirection>ccw</turningDirection>
      <timeConstantUp>0.0125</timeConstantUp>
      <timeConstantDown>0.025</timeConstantDown>
      <maxRotVelocity>1100</maxRotVelocity>
      <motorConstant>5.84e-06</motorConstant>
      <momentConstant>0.06</momentConstant>
      <commandSubTopic>/gazebo/command/motor_speed</commandSubTopic>
      <motorNumber>0</motorNumber>
      <rotorDragCoefficient>0.000175</rotorDragCoefficient>
      <rollingMomentCoefficient>1e-06</rollingMomentCoefficient>
      <motorSpeedPubTopic>/motor_speed/0</motorSpeedPubTopic>
      <rotorVelocitySlowdownSim>10</rotorVelocitySlowdownSim>
    </plugin>
    
    <plugin name='front_left_motor_model' filename='libgazebo_motor_model.so'>
      <robotNamespace/>
      <jointName>prop2</jointName>
      <linkName>link2</linkName>
      <turningDirection>cw</turningDirection>
      <timeConstantUp>0.0125</timeConstantUp>
      <timeConstantDown>0.025</timeConstantDown>
      <maxRotVelocity>1100</maxRotVelocity>
      <motorConstant>5.84e-06</motorConstant>
      <momentConstant>0.06</momentConstant>
      <commandSubTopic>/gazebo/command/motor_speed</commandSubTopic>
      <motorNumber>1</motorNumber>
      <rotorDragCoefficient>0.000175</rotorDragCoefficient>
      <rollingMomentCoefficient>1e-06</rollingMomentCoefficient>
      <motorSpeedPubTopic>/motor_speed/1</motorSpeedPubTopic>
      <rotorVelocitySlowdownSim>10</rotorVelocitySlowdownSim>
    </plugin>
    
    <plugin name='back_left_motor_model' filename='libgazebo_motor_model.so'>
      <robotNamespace/>
      <jointName>prop3</jointName>
      <linkName>link3</linkName>
      <turningDirection>ccw</turningDirection>
      <timeConstantUp>0.0125</timeConstantUp>
      <timeConstantDown>0.025</timeConstantDown>
      <maxRotVelocity>1100</maxRotVelocity>
      <motorConstant>5.84e-06</motorConstant>
      <momentConstant>0.06</momentConstant>
      <commandSubTopic>/gazebo/command/motor_speed</commandSubTopic>
      <motorNumber>2</motorNumber>
      <rotorDragCoefficient>0.000175</rotorDragCoefficient>
      <rollingMomentCoefficient>1e-06</rollingMomentCoefficient>
      <motorSpeedPubTopic>/motor_speed/2</motorSpeedPubTopic>
      <rotorVelocitySlowdownSim>10</rotorVelocitySlowdownSim>
    </plugin>
    
    <plugin name='back_right_motor_model' filename='libgazebo_motor_model.so'>
      <robotNamespace/>
      <jointName>prop4</jointName>
      <linkName>link4</linkName>
      <turningDirection>cw</turningDirection>
      <timeConstantUp>0.0125</timeConstantUp>
      <timeConstantDown>0.025</timeConstantDown>
      <maxRotVelocity>1100</maxRotVelocity>
      <motorConstant>5.84e-06</motorConstant>
      <momentConstant>0.06</momentConstant>
      <commandSubTopic>/gazebo/command/motor_speed</commandSubTopic>
      <motorNumber>3</motorNumber>
      <rotorDragCoefficient>0.000175</rotorDragCoefficient>
      <rollingMomentCoefficient>1e-06</rollingMomentCoefficient>
      <motorSpeedPubTopic>/motor_speed/3</motorSpeedPubTopic>
      <rotorVelocitySlowdownSim>10</rotorVelocitySlowdownSim>
    </plugin>
    
    <plugin name='front_left_down_motor_model' filename='libgazebo_motor_model.so'>
      <robotNamespace/>
      <jointName>prop5</jointName>
      <linkName>link5</linkName>
      <turningDirection>ccw</turningDirection>
      <timeConstantUp>0.0125</timeConstantUp>
      <timeConstantDown>0.025</timeConstantDown>
      <maxRotVelocity>1100</maxRotVelocity>
      <motorConstant>5.84e-06</motorConstant>
      <momentConstant>0.06</momentConstant>
      <commandSubTopic>/gazebo/command/motor_speed</commandSubTopic>
      <motorNumber>4</motorNumber>
      <rotorDragCoefficient>0.000175</rotorDragCoefficient>
      <rollingMomentCoefficient>1e-06</rollingMomentCoefficient>
      <motorSpeedPubTopic>/motor_speed/4</motorSpeedPubTopic>
      <rotorVelocitySlowdownSim>10</rotorVelocitySlowdownSim>
    </plugin>
    
    <plugin name='front_right_down_motor_model' filename='libgazebo_motor_model.so'>
      <robotNamespace/>
      <jointName>prop6</jointName>
      <linkName>link6</linkName>
      <turningDirection>cw</turningDirection>
      <timeConstantUp>0.0125</timeConstantUp>
      <timeConstantDown>0.025</timeConstantDown>
      <maxRotVelocity>1100</maxRotVelocity>
      <motorConstant>5.84e-06</motorConstant>
      <momentConstant>0.06</momentConstant>
      <commandSubTopic>/gazebo/command/motor_speed</commandSubTopic>
      <motorNumber>5</motorNumber>
      <rotorDragCoefficient>0.000175</rotorDragCoefficient>
      <rollingMomentCoefficient>1e-06</rollingMomentCoefficient>
      <motorSpeedPubTopic>/motor_speed/5</motorSpeedPubTopic>
      <rotorVelocitySlowdownSim>10</rotorVelocitySlowdownSim>
    </plugin>
    
    <plugin name='back_right_down_motor_model' filename='libgazebo_motor_model.so'>
      <robotNamespace/>
      <jointName>prop7</jointName>
      <linkName>link7</linkName>
      <turningDirection>ccw</turningDirection>
      <timeConstantUp>0.0125</timeConstantUp>
      <timeConstantDown>0.025</timeConstantDown>
      <maxRotVelocity>1100</maxRotVelocity>
      <motorConstant>5.84e-06</motorConstant>
      <momentConstant>0.06</momentConstant>
      <commandSubTopic>/gazebo/command/motor_speed</commandSubTopic>
      <motorNumber>6</motorNumber>
      <rotorDragCoefficient>0.000175</rotorDragCoefficient>
      <rollingMomentCoefficient>1e-06</rollingMomentCoefficient>
      <motorSpeedPubTopic>/motor_speed/6</motorSpeedPubTopic>
      <rotorVelocitySlowdownSim>10</rotorVelocitySlowdownSim>
    </plugin>
    
    <plugin name='back_left_down_motor_model' filename='libgazebo_motor_model.so'>
      <robotNamespace/>
      <jointName>prop8</jointName>
      <linkName>link8</linkName>
      <turningDirection>cw</turningDirection>
      <timeConstantUp>0.0125</timeConstantUp>
      <timeConstantDown>0.025</timeConstantDown>
      <maxRotVelocity>1100</maxRotVelocity>
      <motorConstant>5.84e-06</motorConstant>
      <momentConstant>0.06</momentConstant>
      <commandSubTopic>/gazebo/command/motor_speed</commandSubTopic>
      <motorNumber>7</motorNumber>
      <rotorDragCoefficient>0.000175</rotorDragCoefficient>
      <rollingMomentCoefficient>1e-06</rollingMomentCoefficient>
      <motorSpeedPubTopic>/motor_speed/7</motorSpeedPubTopic>
      <rotorVelocitySlowdownSim>10</rotorVelocitySlowdownSim>
    </plugin>
    
    <include>
      <uri>model://gps</uri>
      <pose>0.05 0 0.04 0 0 0</pose>
      <name>gps0</name>
    </include>
    <plugin name="gps_plugin" filename="libgazebo_mavlink_gps_plugin.so">
      <robotNamespace/>
      <linkName>base_link</linkName>
      <updateRate>5</updateRate>
    </plugin>
    <joint name='gps0_joint' type='fixed'>
      <child>gps0::link</child>
      <parent>base_link</parent>
    </joint>
    <plugin name='groundtruth_plugin' filename='libgazebo_groundtruth_plugin.so'>
      <robotNamespace/>
    </plugin>
    <plugin name='magnetometer_plugin' filename='libgazebo_magnetometer_plugin.so'>
      <robotNamespace/>
      <pubRate>100</pubRate>
      <noiseDensity>0.0004</noiseDensity>
      <randomWalk>6.4e-06</randomWalk>
      <biasCorrelationTime>600</biasCorrelationTime>
      <magTopic>/mag</magTopic>
    </plugin>
    <plugin name='barometer_plugin' filename='libgazebo_barometer_plugin.so'>
      <robotNamespace/>
      <pubRate>50</pubRate>
      <baroTopic>/baro</baroTopic>
      <baroDriftPaPerSec>0</baroDriftPaPerSec>
    </plugin>
    
    <plugin name='mavlink_interface' filename='libgazebo_mavlink_interface.so'>
      <robotNamespace/>
      <imuSubTopic>/imu</imuSubTopic>
      <magSubTopic>/mag</magSubTopic>
      <baroSubTopic>/baro</baroSubTopic>
      <mavlink_addr>INADDR_ANY</mavlink_addr>
      <mavlink_tcp_port>4560</mavlink_tcp_port>
      <mavlink_udp_port>14560</mavlink_udp_port>
      <serialEnabled>0</serialEnabled>
      <serialDevice>/dev/ttyACM0</serialDevice>
      <baudRate>921600</baudRate>
      <qgc_addr>INADDR_ANY</qgc_addr>
      <qgc_udp_port>14550</qgc_udp_port>
      <sdk_addr>INADDR_ANY</sdk_addr>
      <sdk_udp_port>14540</sdk_udp_port>
      <hil_mode>0</hil_mode>
      <hil_state_level>0</hil_state_level>
      <send_vision_estimation>0</send_vision_estimation>
      <send_odometry>1</send_odometry>
      <enable_lockstep>1</enable_lockstep>
      <use_tcp>1</use_tcp>
      <motorSpeedCommandPubTopic>/gazebo/command/motor_speed</motorSpeedCommandPubTopic>
      
      <control_channels>
        <channel name='rotor1'>
          <input_index>0</input_index>
          <joint_name>prop1</joint_name>
          <input_offset>0</input_offset>
          <input_scaling>1000</input_scaling>
          <zero_position_disarmed>0</zero_position_disarmed>
          <zero_position_armed>100</zero_position_armed>
          <joint_control_type>velocity</joint_control_type>
        </channel>
        <channel name='rotor2'>
          <input_index>1</input_index>
          <joint_name>prop2</joint_name>
          <input_offset>0</input_offset>
          <input_scaling>1000</input_scaling>
          <zero_position_disarmed>0</zero_position_disarmed>
          <zero_position_armed>100</zero_position_armed>
          <joint_control_type>velocity</joint_control_type>
        </channel>
        <channel name='rotor3'>
          <input_index>2</input_index>
          <joint_name>prop3</joint_name>
          <input_offset>0</input_offset>
          <input_scaling>1000</input_scaling>
          <zero_position_disarmed>0</zero_position_disarmed>
          <zero_position_armed>100</zero_position_armed>
          <joint_control_type>velocity</joint_control_type>
        </channel>
        <channel name='rotor4'>
          <input_index>3</input_index>
          <joint_name>prop4</joint_name>
          <input_offset>0</input_offset>
          <input_scaling>1000</input_scaling>
          <zero_position_disarmed>0</zero_position_disarmed>
          <zero_position_armed>100</zero_position_armed>
          <joint_control_type>velocity</joint_control_type>
        </channel>
        <channel name='rotor5'>
          <input_index>4</input_index>
          <joint_name>prop5</joint_name>
          <input_offset>0</input_offset>
          <input_scaling>1000</input_scaling>
          <zero_position_disarmed>0</zero_position_disarmed>
          <zero_position_armed>100</zero_position_armed>
          <joint_control_type>velocity</joint_control_type>
        </channel>
        <channel name='rotor6'>
          <input_index>5</input_index>
          <joint_name>prop6</joint_name>
          <input_offset>0</input_offset>
          <input_scaling>1000</input_scaling>
          <zero_position_disarmed>0</zero_position_disarmed>
          <zero_position_armed>100</zero_position_armed>
          <joint_control_type>velocity</joint_control_type>
        </channel>
        <channel name='rotor7'>
          <input_index>6</input_index>
          <joint_name>prop7</joint_name>
          <input_offset>0</input_offset>
          <input_scaling>1000</input_scaling>
          <zero_position_disarmed>0</zero_position_disarmed>
          <zero_position_armed>100</zero_position_armed>
          <joint_control_type>velocity</joint_control_type>
        </channel>
        <channel name='rotor8'>
          <input_index>7</input_index>
          <joint_name>prop8</joint_name>
          <input_offset>0</input_offset>
          <input_scaling>1000</input_scaling>
          <zero_position_disarmed>0</zero_position_disarmed>
          <zero_position_armed>100</zero_position_armed>
          <joint_control_type>velocity</joint_control_type>
        </channel>
      </control_channels>
    </plugin>
    
    <static>0</static>
    <plugin name='rotors_gazebo_imu_plugin' filename='libgazebo_imu_plugin.so'>
      <robotNamespace/>
      <linkName>/imu_link</linkName>
      <imuTopic>/imu</imuTopic>
      <gyroscopeNoiseDensity>0.00018665</gyroscopeNoiseDensity>
      <gyroscopeRandomWalk>3.8785e-05</gyroscopeRandomWalk>
      <gyroscopeBiasCorrelationTime>1000.0</gyroscopeBiasCorrelationTime>
      <gyroscopeTurnOnBiasSigma>0.0087</gyroscopeTurnOnBiasSigma>
      <accelerometerNoiseDensity>0.00186</accelerometerNoiseDensity>
      <accelerometerRandomWalk>0.006</accelerometerRandomWalk>
      <accelerometerBiasCorrelationTime>300.0</accelerometerBiasCorrelationTime>
      <accelerometerTurnOnBiasSigma>0.196</accelerometerTurnOnBiasSigma>
    </plugin>
    
  </model>
</sdf>
```
