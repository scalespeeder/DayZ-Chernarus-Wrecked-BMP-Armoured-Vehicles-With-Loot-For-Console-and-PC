DayZ Chernarus Wrecked BMP Armoured Vehicles With Loot For Console and PC xml json Mod Instructions & Terms Of Use

Limited Testing on PC Chernarus Local Server DAYZ Version 1.18 Aug 2022.

Created by @scalespeeder. Please report bugs & errors to scalespeeder@gmail.com with screenshots.

Many Thanks To Inclement Dab for his amazing DayZ Editor that makes this all possible: https://steamcommunity.com/sharedfiles/filedetails/?id=2250764298

TERMS OF USE
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS
OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN
AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH
THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Using these modded xml / json files and instructions could break the functioning of your DAYZ server, requiring a reinstall that would wipe
all player progress.

Using these modded files neccessitates increased regular restarts to prevent server crashing.

It is suggested you thoroughly test your server after applying these files to ensure proper
functioning of your server.

I always recomend you validate your files at: https://www.xmlvalidation.com/ and https://jsonformatter.curiousconcept.com/

Instructions:

Click the "Code" button and "Download Zip" on the Github Repository and extract the files on your local PC for access.

(Optional: For advanced users I have included the original DayZ Editor Mod file "lostbattalionBMPs.dze" which can be imported into DayZ Editor Mod on PC for customisation.)

Ensure your DayZ Server has activated the cfggameplay.json. For console users on Nitrado Servers, go to "General Settings" on your server and tick "Enable cfggameplay.json".

On PC Servers add the following line to your serverDZ.cfg:

enableCfgGameplayFile = 1;

(On some PC servers, including Nitrado, the serverDZ.cfg is "hidden", so you need to enable "expert mode" in settings,
then go to "expert settings", which is the serverDZ.cfg. Stop the server before making changes this way.)

Upload "LOSTBMPS.json" from the extracted files to inside the "custom" folder of the mission directory on your server. This file places the BMPs on your map.
(If you haven't got a "custom" folder, create one.)

Open the cfggameplay.json file in the correct mission file for your server and look for the "objectSpawnersArr" line.

This file tells your server to access your custom file.

Edit it to look like this: 

	"objectSpawnersArr": ["custom/LOSTBMPS.json"]
	
If you already are calling custom jsons to spawn items, seperate the files like this:

	"objectSpawnersArr": ["custom/LOSTBMPS.json","custom/anotherfile.json","custom/differentfile.json"]
	
Save your changes & upload if you need to.

Now we need to add a new code snippet to your mapgroupproto.xml that will tell the game what loot to spawn with the BMPs, and where around the vehicle.
Add this code near the top, below </defaults>

<!--Start of BMP Loot details-->
		<group name="StaticObj_Wreck_BMP1" lootmax="15">
				<usage name="Military" />
				<container name="lootFloor" lootmax="15">
						<category name="tools" />
						<category name="containers" />
						<category name="clothes" />
						<category name="weapons" />
						<tag name="floor" />
						<tag name="shelves" />
						<point pos="1.357636 -1.856922 2.039550" range="0.185402" height="1.756649" flags="32" />
						<point pos="3.630615 -1.856922 0.478027" range="0.203125" height="0.507813" flags="32" />
						<point pos="3.128174 -1.856922 0.282226" range="0.237500" height="0.593750" flags="32" />
						<point pos="2.601563 -1.856922 0.026855" range="0.237500" height="0.593750" flags="32" />
						<point pos="2.976563 -1.856922 2.021972" range="0.340625" height="0.851563" flags="32" />
						<point pos="4.462646 -1.856922 -0.474610" range="0.595988" height="1.489970" flags="32" />
						<point pos="2.273926 -1.856922 3.096679" range="0.718352" height="1.795880" flags="32" />
						<point pos="1.722656 -1.856922 -1.948730" range="0.821779" height="2.000004" flags="32" />
						<point pos="5.276123 -1.856922 4.080566" range="0.827611" height="2.000004" flags="32" />
						<point pos="3.192871 -1.856922 -1.159668" range="0.846799" height="2.000004" flags="32" />
						<point pos="-3.063140 -1.856922 3.171630" range="0.816895" height="2.000000" flags="32" />
						<point pos="3.540283 -1.856922 4.118164" range="0.908636" height="2.000004" flags="32" />
						<point pos="0.502686 -1.856922 2.775879" range="0.942924" height="2.000004" flags="32" />
						<point pos="6.488282 -1.856922 2.621093" range="1.069595" height="0.560911" flags="32" />
						<point pos="-0.299072 -1.856922 -1.951172" range="1.199951" height="2.000004" flags="32" />
						<point pos="-5.641358 -1.856922 2.865478" range="1.199951" height="2.000000" flags="32" />
						<point pos="-6.365722 -1.856922 -0.791017" range="1.050690" height="2.000000" flags="32" />
						<point pos="-7.866791 -1.856922 1.028075" range="1.199951" height="2.000000" flags="32" />
						<point pos="-1.301361 -1.856922 3.279541" range="0.930111" height="2.000000" flags="32" />
						<point pos="-2.462616 -1.856922 -2.051270" range="0.965907" height="2.000000" flags="32" />
						<point pos="-4.542145 -1.856922 -1.998291" range="1.114297" height="2.000000" flags="32" />
						<point pos="1.053284 -1.856922 -0.203858" range="1.009568" height="1.428749" flags="32" />
						<point pos="2.162994 -1.856922 1.857910" range="0.489321" height="0.239521" flags="32" />
						<point pos="-4.164428 -1.856922 2.812988" range="0.277910" height="1.145630" flags="32" />
						<point pos="-4.802368 -1.856922 -0.578615" range="0.329033" height="1.024933" flags="32" />
				</container>
		</group>
		
		
		<group name="StaticObj_Wreck_BMP2" lootmax="15">
				<usage name="Military" />
				<container name="lootFloor" lootmax="15">
						<category name="tools" />
						<category name="containers" />
						<category name="clothes" />
						<category name="weapons" />
						<tag name="floor" />
						<tag name="shelves" />
						<point pos="1.357636 -1.856922 2.039550" range="0.185402" height="1.756649" flags="32" />
						<point pos="3.630615 -1.856922 0.478027" range="0.203125" height="0.507813" flags="32" />
						<point pos="3.128174 -1.856922 0.282226" range="0.237500" height="0.593750" flags="32" />
						<point pos="2.601563 -1.856922 0.026855" range="0.237500" height="0.593750" flags="32" />
						<point pos="2.976563 -1.856922 2.021972" range="0.340625" height="0.851563" flags="32" />
						<point pos="4.462646 -1.856922 -0.474610" range="0.595988" height="1.489970" flags="32" />
						<point pos="2.273926 -1.856922 3.096679" range="0.718352" height="1.795880" flags="32" />
						<point pos="1.722656 -1.856922 -1.948730" range="0.821779" height="2.000004" flags="32" />
						<point pos="5.276123 -1.856922 4.080566" range="0.827611" height="2.000004" flags="32" />
						<point pos="3.192871 -1.856922 -1.159668" range="0.846799" height="2.000004" flags="32" />
						<point pos="-3.063140 -1.856922 3.171630" range="0.816895" height="2.000000" flags="32" />
						<point pos="3.540283 -1.856922 4.118164" range="0.908636" height="2.000004" flags="32" />
						<point pos="0.502686 -1.856922 2.775879" range="0.942924" height="2.000004" flags="32" />
						<point pos="6.488282 -1.856922 2.621093" range="1.069595" height="0.560911" flags="32" />
						<point pos="-0.299072 -1.856922 -1.951172" range="1.199951" height="2.000004" flags="32" />
						<point pos="-5.641358 -1.856922 2.865478" range="1.199951" height="2.000000" flags="32" />
						<point pos="-6.365722 -1.856922 -0.791017" range="1.050690" height="2.000000" flags="32" />
						<point pos="-7.866791 -1.856922 1.028075" range="1.199951" height="2.000000" flags="32" />
						<point pos="-1.301361 -1.856922 3.279541" range="0.930111" height="2.000000" flags="32" />
						<point pos="-2.462616 -1.856922 -2.051270" range="0.965907" height="2.000000" flags="32" />
						<point pos="-4.542145 -1.856922 -1.998291" range="1.114297" height="2.000000" flags="32" />
						<point pos="1.053284 -1.856922 -0.203858" range="1.009568" height="1.428749" flags="32" />
						<point pos="2.162994 -1.856922 1.857910" range="0.489321" height="0.239521" flags="32" />
						<point pos="-4.164428 -1.856922 2.812988" range="0.277910" height="1.145630" flags="32" />
						<point pos="-4.802368 -1.856922 -0.578615" range="0.329033" height="1.024933" flags="32" />
				</container>
		</group>
		<!--End of BMP loot details-->
		
Save and / or reupload if necessary.
	
Next we add loot to the specific BMPs by adding the following code snippet to the top of your mapgrouppos.xml file, after <map> 

	<!--start of BMP location details-->
	<group name="StaticObj_Wreck_BMP1" pos="124.603996 457.114990 11028.200195" rpy="-0.500000 -0.499340 -150.662003" a="-119.338"/>
	<group name="StaticObj_Wreck_BMP2" pos="12410.400391 141.082993 12386.400391" rpy="9.000000 0.499917 7.011239" a="82.9888"/>
	<group name="StaticObj_Wreck_BMP2" pos="276.230988 164.719482 2696.570068" rpy="16.999996 -1.500000 176.774979" a="-86.775"/>
	<group name="StaticObj_Wreck_BMP1" pos="384.783997 101.083000 4034.219971" rpy="0.000000 1.500000 25.575298" a="64.4247"/>
	<group name="StaticObj_Wreck_BMP2" pos="885.044006 163.945999 5067.580078" rpy="10.999999 -1.500000 123.179001" a="-33.179"/>
	<group name="StaticObj_Wreck_BMP1" pos="342.984009 282.041992 9080.040039" rpy="-2.500000 3.000000 -160.460983" a="-109.539"/>
	<group name="StaticObj_Wreck_BMP2" pos="2998.929932 250.027954 13888.000000" rpy="8.499999 6.500000 0.000000" a="90"/>
	<group name="StaticObj_Wreck_BMP1" pos="8836.650391 340.471832 14956.599609" rpy="3.000000 3.500000 0.000000" a="90"/>
	<group name="StaticObj_Wreck_BMP2" pos="13438.808594 129.813980 15159.889648" rpy="7.754480 8.385969 0.000000" a="90"/>
	<group name="StaticObj_Wreck_BMP1" pos="14068.500000 90.070000 14251.500000" rpy="-1.032490 -0.552959 -51.793396" a="141.793"/>
	<group name="StaticObj_Wreck_BMP2" pos="11696.797852 123.570686 8695.339844" rpy="5.510670 6.918570 -95.942307" a="-174.058"/>
	<!--end of BMP location details-->
	
Save your changes & upload if you need to.

Restart your server and the new BMPs will appear immediatly, and then they will slowly stock with loot.

Thanks, Rob.
