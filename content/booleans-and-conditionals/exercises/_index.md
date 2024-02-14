+++
title = "Exercises: Booleans and Conditionals"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

For the exercises, open up the `booleans-and-conditionals` directory in `data-analysis-projects`.

To answer questions 1 and 2, code your work in `exercises01.py`.

1. **Assign the following variables for our space shuttle**

   | Variable Name | Value |
   |---------------|-------|
   | `engine_indicator_light` | red blinking |
   | `space_suits_on` | True |
   | `shuttle_cabin_ready` | True |
   | `crew_status` | `space_suits_on` and `shuttle_cabin_ready` |
   | `computer_status_code` | 200 |
   | `shuttle_speed` | 15000 |

   {{% expand "Check your solution" %}}
   
   ```python {linenos=table}
   engine_indicator_light = "red blinking"
   space_suits_on = True
   shuttle_cabin_ready = True
   crew_status = space_suits_on and shuttle_cabin_ready
   computer_status_code = 200
   shuttle_speed = 15000
   ```

   {{% /expand %}} 

1. **Examine the code below. What will be printed to the console?**

   Use the value of `engine_indicator_light` defined above to answer this
   question.

   ```python {linenos=table}
   if engine_indicator_light == "green": 
      print("engines have started")
   elif engine_indicator_light == "green blinking": 
      print("engines are preparing to start")
   else:
      print("engines are off")
   ```

For questions 3 and 4, code in `exercises02.py`.

1. **Write conditional expressions to satisfy the safety rules.** 

   Use the variables defined from the table above to satisfy the rules listed below.

   1. `crew_status`

      - If the value is `True`, print `"Crew Ready"`
      - Else print `"Crew Not Ready"`

      {{% expand "Check your solution" %}}
      
      ```python {linenos=table}
      if crew_status:
         print("Crew Ready")
      else:
         print("Crew Not Ready")
      ```

      {{% /expand %}}

   1. `computer_status_code`

      - If the value is `200`, print
        `"Please stand by. Computer is rebooting."`
      - Else if the value is `400`, print `"Success! Computer online."`
      - Else print `"ALERT: Computer offline!"`

      {{% expand "Check your solution" %}}
      
      ```python {linenos=true}
      if computer_status_code == 200:
         print("Please stand by. Computer is rebooting.")
      elif computer_status_code == 400:
         print("Success! Computer online.")
      else:
         print("ALERT: Computer offline!")
      ```

      {{% /expand %}}

   1. `shuttle_speed`

      - If the value is `> 17500`, print
        `"ALERT: Escape velocity reached!"`
      - Else if the value is `< 8000`, print
        `"ALERT: Cannot maintain orbit!"`
      - Else print `"Stable speed"`

      {{% expand "Check your solution" %}}
      
      ```python {linenos=table}
      if shuttle_speed > 17500:
         print("ALERT: Escape velocity reached!")
      elif shuttle_speed < 8000:
         print("ALERT: Cannot maintain orbit!")
      else:
         print("Stable speed.")
      ```

      {{% /expand %}}

1. **PREDICT**

   Do these code blocks produce the same result? Answer Yes or No.

   ```python {linenos=table}
   if crew_status and computer_status_code == 200 and space_suits_on:
      print("all systems go")
   else:
      print("WARNING. Not ready")
   ```

   ```python {linenos=table}
   if crew_status != True or computer_status_code != 200 or not(space_suits_on):
      print("WARNING. Not ready")
   else:
      print("all systems go")
   ```

For exercises 5 and 6, code in `exercises03.py`. 

1. **Monitor the shuttle's fuel status.**

   Implement the checks below using `if` / `elif` / `else`
   statements. Order is important when working with conditionals, and the
   checks below are NOT written in the correct sequence. Please read ALL of the
   checks before coding and then decide on the best order for the conditionals.

   1. If `fuel_level` is above 20000 AND `engine_temperature` is at or below
      2500, print `"Full tank. Engines good."`
   1. If `fuel_level` is above 10000 AND `engine_temperature` is at or below
      2500, print `"Fuel level above 50%.  Engines good."`
   1. If `fuel_level` is above 5000 AND `engine_temperature` is at or below
      2500, print `"Fuel level above 25%. Engines good."`
   1. If `fuel_level` is at or below 5000 OR `engine_temperature` is above
      2500, print `"Check fuel level. Engines running hot."`
   1. If `fuel_level` is below 1000 OR `engine_temperature` is above 3500 OR
      `engine_indicator_light` is red blinking, print `"ENGINE FAILURE
      IMMINENT!"`
   1. Otherwise, print `"Fuel and engine status pending..."`

   {{% expand "Check your solution" %}}
   
   ```python {linenos=table}
   if fuel_level < 1000 or engine_temperature > 3500 or engine_indicator_light == "red blinking":
      print("ENGINE FAILURE IMMINENT!")
   elif fuel_level <= 5000 or engine_temperature > 2500:
      print("Check fuel level. Engines running hot.")
   elif fuel_level > 20000 and engine_temperature <= 2500:
      print("Full tank. Engines good.")
   elif fuel_level > 10000 and engine_temperature <= 2500:
      print("Fuel level above 50%. Engines good.")
   elif fuel_level > 5000 and engine_temperature <= 2500:
      print("Fuel level above 25%. Engines good.")
   else:
      print("Fuel and engine status pending...")
   ```

   {{% /expand %}}

1. **Final bit of fun!**

   The shuttle should only launch if the fuel tank is full and the engine check
   is OK. *However*, let's establish an override command to ignore any warnings
   and send the shuttle into space anyway!

   1. Create the variable `command_override`, and set it to be `true` *or*
      `false`.

      If `command_override` is `False`, then the shuttle should only launch
      if the fuel and engine check are OK.

      If `command_override` is `True`, then the shuttle will launch
      regardless of the fuel and engine status.

   1. Code the following `if` / `else` check:

      If `fuel_level` is above 20000 AND `engine_indicator_light` is NOT
      red blinking OR `command_override` is true print `"Cleared to
      launch!"`

      Else print `"Launch scrubbed!"`

## Submitting Your Work

Commit and push your work to GitHub. Copy and paste the URL to your GitHub repository on the submission page for the exercises in Canvas.