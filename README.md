# androidtv
Custom Home Assistant media_player component for generic Android devices.

Relies on python-androidtv module for state detection
 - Original Repo can be found [here](https://github.com/JeffLIrion/python-androidtv)
 - My version can be found [here](https://github.com/caffeinatedMike/python-androidtv)
 
For testing we will be better off using my version as we can make edits to it before doing the final PR to that repository
What that means for development:
 - Firstly, we have to change [Line 32](https://github.com/caffeinatedMike/androidtv/blob/master/androidtv.py#L32) of androidtv.py from `REQUIREMENTS = ['adb-homeassistant', 'androidtv']` to `REQUIREMENTS = ['adb-homeassistant']`
 - Second, we have to have the following folder structure
   - custom_components/
     - media_player/
       - androidtv.py
       - androidtv/
         - \_\_init\_\_.py (taken from the python-androidtv repo's [androidtv folder](https://github.com/caffeinatedMike/python-androidtv/tree/master/androidtv))
 - Lastly, we have to change the reference to the python-androidtv module on [Line 241](https://github.com/caffeinatedMike/androidtv/blob/master/androidtv.py#L241) to import locally, like so
   - Replace `from androidtv import AndroidTV` with `from .androidtv import AndroidTV`
