# Code signing
Code signing is the process to ensure an app's integrity and authenticity before it can be installed on a device

# Certificate
Developer's identity, consists of developer's **public key** and **signed signature** of a trust authority (Apple)
A certificate is associated with eveloper's private key. This private key is used to sign the app's executable to create a signature of the executable. 

# Provisioning profile
Dictates which devices can run and app with what capabilities. The profile is signed by Apple and contains a reference to the certificate(s) that is supposed to be used to sign the app. 

# Signing process
1. XCode compiles the project
2. XCode uses the cert's private key to sign the hashed the executable. 
3. XCode checks the provisioning profile: appID, deviceID, capabilities, etc.. and verify with the said cert to see if the profile and cert is correctly aligned
4. App can be packaged and run or distributed. 

# Takeaway team practices
1. Add developer account to the team. 
2.1 Each developer uses their own certificates to obtain their own provisioning profile
2.2. Or use a shared profile for all developers in the team (not secured)
3.1. For small team, use Xcode's automatic manage
3.2. For big teams, use CI tool.

# (Bonus) App thinning
App thinning is the process of reducing the size of the app on user's device, including
## App slicing: Remove un-needed resources for dedicated platform/devices. (e.g: 2x,3x images,etc..)
<img width="336" alt="image" src="https://github.com/hoangelec/Knowledge-consolidation/assets/9737526/5fb87bfc-f22b-4620-ac22-ca999bf34b76">

## On-demand resources
- The capability for the application to download addtional resources upon installation.
<img width="530" alt="image" src="https://github.com/hoangelec/Knowledge-consolidation/assets/9737526/e31751e2-11ff-4a19-a678-b23cf079c6a4">

## Bitcode (deprecated)
Intermediate presentation of the project code, can be sent to Apple for their optimization (new compiler/new architecture, etc...)

# dSYM
Stands for **Debug Symbol**. This file contains the debug symbol for the binary (function name, variable, lines, etc..) that is critical for debugging purposes
## dSYM Distribution:
- XCode relies on DEBUG_INFORMATION_FORMAT flag to determine where the dSYM is embeded inside the app's binary or not.
- If build is in Debug mode, the dSYM is stored right inside binary, supporting live Debugging with XCode
- If build is in prod mode, dSYM is saved separatedly to reduce binary size




