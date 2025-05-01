# xhski-menu
my mod menu
mods at botton
using System;
using Photon.Pun;
using StupidTemplate.Classes;
using StupidTemplate.Mods;
using UnityEngine;
using xHSKI_MENU.Menu;
using xHSKI_MENU.Mods;
using xHSKI_MENU.Mods.Environment;
using xHSKI_MENU.Mods.flystufff;
using xHSKI_MENU.Mods.lagspike;
using xHSKI_MENU.Mods.lonarmsstuff;
using xHSKI_MENU.Mods.movement;
using xHSKI_MENU.Mods.platforms;
using xHSKI_MENU.Mods.safety;
using xHSKI_MENU.Mods.servers;
using xHSKI_MENU.Mods.speedstuff;
using xHSKI_MENU.Mods.view;
using xHSKI_MENU.Mods.waterballonstuff;
using static StupidTemplate.Settings;

namespace StupidTemplate.Menu
{
    internal class Buttons
    {
        public static ButtonInfo[][] buttons = new ButtonInfo[][]
        {
            new ButtonInfo[] { // Main Mods
                new ButtonInfo { buttonText = "Settings", method = () => SettingsMods.EnterSettings(), isTogglable = false, toolTip = "Opens the main settings page for the menu." },
                new ButtonInfo { buttonText = "BASIC", method = () => SettingsMods.basic(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "advantages", method = () => SettingsMods.advantages(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "visuals", method = () => SettingsMods.visuals(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "movement", method = () => SettingsMods.movement(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "overpowered", method = () => SettingsMods.overpowered(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "safety", method = () => SettingsMods.safety(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "fun", method = () => SettingsMods.fun(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "guardian", method = () => SettingsMods.guardian(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "random", method = () => SettingsMods.random(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "egg camera gun", method = () => CameraEggGun.CameraEggGunMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "togglable placeholder 9" },
                new ButtonInfo { buttonText = "regular placeholder 9", isTogglable = false },
            },

            new ButtonInfo[] { // Settings
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "Menu", method = () => SettingsMods.MenuSettings(), isTogglable = false, toolTip = "Opens the settings for the menu." },
                new ButtonInfo { buttonText = "Projectile", method = () => SettingsMods.ProjectileSettings(), isTogglable = false, toolTip = "Opens the projectile settings for the menu." },
            },

            new ButtonInfo[] { // Menu Settings
                new ButtonInfo { buttonText = "Return to Settings", method = () => SettingsMods.EnterSettings(), isTogglable = false, toolTip = "Returns to the main settings page for the menu." },
                new ButtonInfo { buttonText = "Right Hand", enableMethod = () => SettingsMods.RightHand(), disableMethod = () => SettingsMods.LeftHand(), toolTip = "Puts the menu on your right hand." },
                new ButtonInfo { buttonText = "Notifications", enableMethod = () => SettingsMods.EnableNotifications(), disableMethod = () => SettingsMods.DisableNotifications(), enabled = !disableNotifications, toolTip = "Toggles the notifications." },
                new ButtonInfo { buttonText = "FPS Counter", enableMethod = () => SettingsMods.EnableFPSCounter(), disableMethod = () => SettingsMods.DisableFPSCounter(), enabled = fpsCounter, toolTip = "Toggles the FPS counter." },
                new ButtonInfo { buttonText = "Disconnect Button", enableMethod = () => SettingsMods.EnableDisconnectButton(), disableMethod = () => SettingsMods.DisableDisconnectButton(), enabled = disconnectButton, toolTip = "Toggles the disconnect button." },
            },

            new ButtonInfo[] { // Projectile Settings
                new ButtonInfo { buttonText = "Return to Settings", method = () => SettingsMods.MenuSettings(), isTogglable = false, toolTip = "Opens the settings for the menu." },
            },
            new ButtonInfo[] { // BASIC
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "Environment", method = () => SettingsMods.Environment(), isTogglable = false, toolTip = "you should know." },
            },

            new ButtonInfo[] { // advantages
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "nametag", method = () => NameESP.UpdateNameESP(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "platforms", method = () => platform.PlatformMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "sticky platforms", method = () => StickyPlatform.StickyPlatformsMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "invis platforms", method = () => invisplat.Invizplatforms(), toolTip = "invis plats. UND", isTogglable = true },
                new ButtonInfo { buttonText = "fly stuff", method = () => SettingsMods.flystuff(), isTogglable = false, toolTip = "Opens the main settings page for the menu." },
                new ButtonInfo { buttonText = "longarm stuff", method = () => SettingsMods.longarmstuff(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "speed stuff", method = () => SettingsMods.speedstuff(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "flystuff", method = () => SettingsMods.flystuff(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "noclip fly", method = () => noclipfly.NoclipFlyMod(), toolTip = "fly and go out the map. UND", isTogglable = true },
                new ButtonInfo { buttonText = "esp stuff", method = () => SettingsMods.espstuff(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "carmonke", method = () => carmonke.carmonkeMod(), toolTip = "yor a monke car. UND", isTogglable = true },
                new ButtonInfo { buttonText = "noclip", method = () => noclip.noclipMod(), toolTip = "seee the players. UND", isTogglable = true },
                new ButtonInfo { buttonText = "tp gun", method = () => TPGun.TPGunMod(), toolTip = "seee the players. UND", isTogglable = true },
                new ButtonInfo { buttonText = "regular placeholder 9", isTogglable = false },
            },
            new ButtonInfo[] { // visuals
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "draw gun", method = () => Drawgun.Draw(), toolTip = "smooths your rig. UND", isTogglable = true },
                new ButtonInfo { buttonText = "rainbow drawgun", method = () => raingbowDrawgun.rainbowDrawgunMod(), toolTip = "smooths your rig. UND", isTogglable = true },
                new ButtonInfo { buttonText = "body stuff", method = () => SettingsMods.bodystuff(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "trail stuff", method = () => SettingsMods.trailstuff(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "smooth Rig", method = () => smoothrig.SmoothRigMod(), toolTip = "smooths your rig. UND", isTogglable = true },
                new ButtonInfo { buttonText = "robux gun", method = () => RobuxBoxSpawner.RobuxBoxMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "blackholegun", method = () => BlackholeGun.blackholegunmod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "cube gun", method = () => CubeSpawner.SpawnCubeMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "random cube gun", method = () => randomCubeSpawner.randomSpawnCubeMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "firework gun", method = () => FireworkSpawner.SpawnFireworksMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "fish gun", method = () => FishSpawner.SpawnFish(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "ray tracing", method = () => RayTraceVisualizerMod.FakeRaytraceMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "tracers", method = () => TracerMod.TracerUpdateMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "circle gun", method = () => CircleGun.CircleGunMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "throwable ball", method = () => ThrowableBall.ThrowBall(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "regular placeholder 9", isTogglable = false },
            },
            new ButtonInfo[] { // movement
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "stickywalls", method = () => StickyWall.StickyWallMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "WASD", method = () => wasd.WASDFly(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "regular placeholder 9", isTogglable = false },
            },
            new ButtonInfo[] { // overpowered
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "Projectiles", method = () => SettingsMods.Projectiles(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "critter stuff", method = () => SettingsMods.critterstuff(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "camera stuff", method = () => SettingsMods.camerastuff(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "snowball gun", method = () => SnowballGun.SnowballGunMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "lag stuff", method = () => SettingsMods.lagstuff(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "paintball stuff", method = () => SettingsMods.paintballstuff(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "waterballon stuff", method = () => SettingsMods.waterballon(), isTogglable = false, toolTip = "clientsided sadly." },
                new ButtonInfo { buttonText = "glider stuff", method = () => SettingsMods.gliderstuff(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "water stuff", method = () => SettingsMods.waterstuff(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "bat gun", method = () => BatGun.BatGunMod(), toolTip = "stops from getting banned. UND", isTogglable = true },
                new ButtonInfo { buttonText = "bat grab", method = () => Batgrab.batgrabMod(), toolTip = "stops from getting banned. UND", isTogglable = true },
                new ButtonInfo { buttonText = "regular placeholder 9", isTogglable = false },
            },
            new ButtonInfo[] { // safety
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "antireport", method = () => antireport.AntiReportMod(), toolTip = "stops from getting banned. UND", isTogglable = true },
                new ButtonInfo { buttonText = "antireport [OP]", method = () => AntiReportOP.OPAntiReport(), toolTip = "stops from getting banned. UND", isTogglable = true },
                new ButtonInfo { buttonText = "antireport0culus[may work]", method = () => antioclusreport.antiOculusreport(), toolTip = "may stop. UND", isTogglable = true },
                new ButtonInfo { buttonText = "Servers", method = () => SettingsMods.servers(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "random name", method = () => RandomNameMod.randomname(), toolTip = "stops from getting banned. UND", isTogglable = true },
                new ButtonInfo { buttonText = "nofinger movement", method = () => DisableFingerMovement.DisableFingerMod(), toolTip = "stops from getting banned. UND", isTogglable = true },
                new ButtonInfo { buttonText = "regular placeholder 9", isTogglable = false },
            },
            new ButtonInfo[] { // fun
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "TROLLING", method = () => SettingsMods.TROLLING(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "grab rig", method = () => grabrig.GrabRigMod(), toolTip = "grab yourself. UND", isTogglable = true },
                new ButtonInfo { buttonText = "ghost", method = () => Ghost.invisablemod(), toolTip = "be a ghost. UND", isTogglable = true },
                new ButtonInfo { buttonText = "neck snap", method = () => SelfNeckSnap.NeckSnapMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "RGBmonke", method = () => RGBMonke.RGBMonkeMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "bouncy", method = () => Bouncy.ApplyBounce(), toolTip = "seee the players. UND", isTogglable = true },
                new ButtonInfo { buttonText = "spin monke", method = () => spinmonke.SpinnyMonkeMod(), toolTip = "seee the players. UND", isTogglable = true },
                new ButtonInfo { buttonText = "regular placeholder 9", isTogglable = false },
            },
            new ButtonInfo[] { // guardian
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "regular placeholder 9", isTogglable = false },
            },
            new ButtonInfo[] { // random
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "GRAVITY", method = () => SettingsMods.gravity(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "gravity flip", method = () => gravityFlip.Update(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "antilag", method = () => AntiLag.AntiLagMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "60HZ", method = () => SixtyHzMode.ToggleSixtyHz(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "ai performance", method = () => DynamicFrameRateAdjuster.AdjustFrameRate(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "vfx spammer", method = () => VFXSpawner.VFXSpawnerMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "regular placeholder 9", isTogglable = false },
            },

            new ButtonInfo[] { // Projectiles
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "go back to overpowered", method = () => SettingsMods.overpowered(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "regular placeholder 9", isTogglable = false },
            },

            new ButtonInfo[] { // critterstuff
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "go back to overpowered", method = () => SettingsMods.overpowered(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "critter minigun", method = () => CritterMinigun.ShootCritterGun(), toolTip = "What your mod does. UND", isTogglable = true },
            },
            new ButtonInfo[] { // camerastuff
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "go back to overpowered", method = () => SettingsMods.overpowered(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "egg camera gun", method = () => CameraEggGun.CameraEggGunMod(), toolTip = "What your mod does. UND", isTogglable = true },
            },
            new ButtonInfo[] { // lagstuff
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "go back to overpowered", method = () => SettingsMods.overpowered(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "lagspikeall", method = () => lagspikeall.SimulateLagSpike(), toolTip = "lags people. IDK", isTogglable = true },
                new ButtonInfo { buttonText = "lagspikeaura", method = () => LagAuraMod.TriggerLagAura(), toolTip = "lags people. IDK", isTogglable = true },
            },
            new ButtonInfo[] { // speedboost
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "speedboost [SLOW]", method = () => slowspeedboost.SlowSpeedboostMod(), toolTip = "lags people. IDK", isTogglable = true },
                new ButtonInfo { buttonText = "speedboost [NORMAL]", method = () => normalspeedboost.NormalSpeedboostMod(), toolTip = "lags people. IDK", isTogglable = true },
                new ButtonInfo { buttonText = "speedboost [MOSA]", method = () => mosaspeedboost.MosaSpeedboostMod(), toolTip = "lags people. IDK", isTogglable = true },
                new ButtonInfo { buttonText = "speedboost [FAST]", method = () => fastspeedboost.FastSpeedboostMod(), toolTip = "lags people. IDK", isTogglable = true },
                new ButtonInfo { buttonText = "speedboost [SUPER]", method = () => superspeedboost.SuperSpeedboostMod(), toolTip = "lags people. IDK", isTogglable = true },
                new ButtonInfo { buttonText = "speedboost [MEGA]", method = () => megaspeedboost.MegaSpeedboostMod(), toolTip = "lags people. IDK", isTogglable = true },
                new ButtonInfo { buttonText = "speedboost [ULTRA]", method = () => ultraspeedboost.UltraSpeedboostMod(), toolTip = "lags people. IDK", isTogglable = true },
                new ButtonInfo { buttonText = "speedboost [HYPER]", method = () => hyperspeedboost.HyperSpeedboostMod(), toolTip = "lags people. IDK", isTogglable = true },
                new ButtonInfo { buttonText = "speedboost [GOD]", method = () => godspeedboost.GodSpeedboostMod(), toolTip = "lags people. IDK", isTogglable = true },
            },
            new ButtonInfo[] { // Environment
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "DAY Time", method = () => DAYtime.DayTime(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "MORNING Time", method = () => morningtime.MorningTimeMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "EVENING time", method = () => eveningtime.EveningTimeMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "NIGHT time", method = () => nighttime.NightTimeMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "RAIN time", method = () => Raintime.RainMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "NORAIN time", method = () => norain.NoRainMod(), toolTip = "What your mod does. UND", isTogglable = true },
            },
            new ButtonInfo[] { // waterballon stuff
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "waterballongun", method = () => WaterBalloonGun.WaterBalloonGunMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "waterballonminigun", method = () => WaterBalloonMinigun.WaterBalloonMinigunMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "waterballonpee", method = () => PeeWaterBalloon.SpawnPeeWaterBalloonMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "waterballonrain", method = () => WaterBalloonRain.TriggerWaterBalloonRain(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "waterballon tornado", method = () => WaterballoonTornado.SpawnTornado(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "waterballon pointer", method = () => WaterBalloonpointer.WaterBalloonpointerMod(), toolTip = "What your mod does. UND", isTogglable = true },

            },
            new ButtonInfo[] { // fly stuff
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "fly[SLOW]", method = () => slowfly.slowflyMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "fly[NORMAL]", method = () => normalfly.normalflyMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "fly[FAST]", method = () => fastfly.fastflyMod(), toolTip = "What your mod does. UND", isTogglable = true },
                new ButtonInfo { buttonText = "fly[INSANE]", method = () => insanefly.insaneflyMod(), toolTip = "What your mod does. UND", isTogglable = true },
            },
            new ButtonInfo[] { // TROLLING
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "lag gun", method = () => LagGun.LaggunMod(), toolTip = "What your mod does. UND", isTogglable = true },
            },
            new ButtonInfo[] { // GRAVITY
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "low gravity", method = () => lowGravity.lowGravityMod(), toolTip = "What your mod does. UND", isTogglable = true },
            },
            new ButtonInfo[] { // longarmstuff
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "longarms [RESET]", method = () => resetArms.resetArmsMod(), toolTip = "yor a monke car. UND", isTogglable = true },
                new ButtonInfo { buttonText = "longarms [STEAM]", method = () => steamlongarms.steamlongarmsMod(), toolTip = "yor a monke car. UND", isTogglable = true },
                new ButtonInfo { buttonText = "longarms [COMP]", method = () => compLongArms.compLongArmsMod(), toolTip = "yor a monke car. UND", isTogglable = true },
                new ButtonInfo { buttonText = "longarms [STICK]", method = () => sticklongarms.StickArmsMod(), toolTip = "yor a monke car. UND", isTogglable = true },

            },
            new ButtonInfo[] { // SERVERS
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "server[EU]", method = () => euservers.EUServersMod(), toolTip = "server. UND", isTogglable = true },
                new ButtonInfo { buttonText = "server[US]", method = () => usserver.USServersMod(), toolTip = "server. UND", isTogglable = true },
                new ButtonInfo { buttonText = "server[USW]", method = () => uswserver.USWServersMod(), toolTip = "server. UND", isTogglable = true },
            },
            new ButtonInfo[] { // paintballstuff
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "paintball gun", method = () => PaintballGun.paintballgunMod(), toolTip = "yor a monke car. UND", isTogglable = true },
            },
            new ButtonInfo[] { // gliderstuff
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "go back to overpowered", method = () => SettingsMods.overpowered(), isTogglable = false, toolTip = "you should know." },
                new ButtonInfo { buttonText = "gliderall", method = () => GliderMagnet.PullGliders(), toolTip = "stops from getting banned. UND", isTogglable = true },
                new ButtonInfo { buttonText = "glider speedboost", method = () => GliderSpeedBoostToggle.ToggleGliderSpeedBoost(), toolTip = "press a to use. UND", isTogglable = true },
                new ButtonInfo { buttonText = "glider fling", method = () => GliderFling.FlingAllGliders(), toolTip = "press a to use. UND", isTogglable = true },
            },
            new ButtonInfo[] { // waterstuff
                 new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                 new ButtonInfo { buttonText = "waterspray", method = () => WaterSprayEffect.waterSprayMod(), toolTip = "stops from getting banned. UND", isTogglable = true },
            },
            new ButtonInfo[] { // espstuff
                 new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                 new ButtonInfo { buttonText = "Sphere esp", method = () => Sphereesp.SphereHeadESP(), toolTip = "seee the players. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "Box esp", method = () => Boxesp.BoxESPMod(), toolTip = "seee the players. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "lavamonke Box esp", method = () => lavamonkeBoxesp.lavemonkeBoxESPMod(), toolTip = "seee the players. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "beacon esp", method = () => BeaconESP.BeaconESPMod(), toolTip = "seee the players. UND", isTogglable = true },
            },
            new ButtonInfo[] { // bodystuff
                new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                new ButtonInfo { buttonText = "transparent", method = () => TransparentBody.TransparentBodyMod(), toolTip = "seee the players. UND", isTogglable = true },
                new ButtonInfo { buttonText = "RGB", method = () => RGBbody.RGBbodyMod(), toolTip = "seee the players. UND", isTogglable = true },
            },
            new ButtonInfo[] { // trailstuff
                 new ButtonInfo { buttonText = "Home", method = () => Global.ReturnHome(), isTogglable = false, toolTip = "Returns to the main page of the menu." },
                 new ButtonInfo { buttonText = "trail [white]", method = () => Trail.TrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [red]", method = () => RedTrail.RedTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [yellow]", method = () => YellowTrail.YellowTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [purple]", method = () => PurpleTrail.PurpleTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [blue]", method = () => blueTrail.blueTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [orange]", method = () => OrangeTrail.OrangeTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [black]", method = () => BlackTrail.BlackTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [rainbow]", method = () => RainbowTrail.RainbowTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [flame]", method = () => FlameTrail.FlameTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [electric]", method = () => ElectricTrail.ElectricTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [cosmic]", method = () => CosmicTrail.CosmicTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [ghostly]", method = () => GhostlyTrail.GhostlyTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [lava]", method = () => LavaTrail.LavaTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [firework]", method = () => FireworksTrail.FireworksTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [speedboost]", method = () => SpeedBoostTrail.SpeedBoostTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [bubbly]", method = () => BubblyTrail.BubblyTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
                 new ButtonInfo { buttonText = "trail [retro]", method = () => PixelatedRetroTrail.PixelatedRetroTrailMod(), toolTip = "flame on your back. UND", isTogglable = true },
            }
        };
    }
}
