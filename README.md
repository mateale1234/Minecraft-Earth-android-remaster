# Minecraft-Earth-android-remaster
Files and configuration for minecraft earth android after June 30, 2021

# Setting up the Minecraft Earth server infrastructure.
Getting all the parts

to start, ensure that you have built copies of all the required components downloaded:

    A built copy of the Api (you are in this repo), which you can fetch from our jenkins
    Our ApiData repo, or your own data. In addition, you'll need the Minecraft Earth resource pack file, renamed to vanilla.zip and placed in the resourcepacks subfolder of the ApiData repo. You can procure the resourcepack from here, provided you're setting up before June 30th, 2021. Rename your clone to data, and place it next to your Api executable.
    Our fork of Cloudburst. Builds of this can be found here. This jar can be located elsewhere from the Api things.
    Run Cloudburst once to generate the file structure.
    In the plugins folder, you'll need GenoaPlugin, and GenoaAllocatorPlugin. The CI for this can be found here and here. Note: make sure to rename your GenoaAllocatorPlugin.jar to ZGenoaAllocatorPlugin.jar, or you will run into issues with class loading

Setting up

On the cloudburst side:

    within the plugins folder, create a GenoaAllocatorPlugin folder, and in there, make a key.txt file containing a base64 encryption key. An example key is

/g1xCS33QYGC+F2s016WXaQWT8ICnzJvdqcVltNtWljrkCyjd5Ut4tvy2d/IgNga0uniZxv/t0hELdZmvx+cdA==

    edit the cloudburst.yml file, and chan ge the core api url to the url your Api will be accessible from
    on the Api side, go to data/config/apiconfig.json, and add the following:

"multiplayerAuthKeys": {
        "Your cloudburst server IP here": "the same key you put in key.txt earlier"
 }

    Start up the Api
    Start up cloudburst. After a short while the Api should mention a server being connected.
    If you run into issues, retrace your steps, or contact us on discord
    If everything works, your next challenge is to get Minecraft Earth to talk to your Api. If you're on Android, you can utilize our patcher. If you're on IOS, the only way to accomplish this without jailbreak is to utilize a DNS, such as bind9. Setup for that goes beyond the scope of this guide
# Link to resourse repo

1.Jenkis with files: https://ci.rtm516.co.uk/job/ProjectEarth/
2.Cloudburst: https://ci.opencollab.dev//job/NukkitX/job/Server/job/master/
3.Data import from offical server before 30.06.2021; import.projectearth.dev
4.Page project earth: https://projectearth.dev/
5.Github: https://github.com/Project-Earth-Team
6.Resourse: https://github.com/mateale1234/Minecraft-Earth-resourse
