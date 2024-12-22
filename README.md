# cybersteve777.github.io - currently it's a test repo for PvZ2C lawnstrings server, simplified to just pushing raw file to the directory.

## Credits:
 - nineteendo - for his pyvz2 tool
 - Haruma - for his help with explaining algorithms 
 - vi_i_guess - for general file structure explanation [here](https://github.com/viiguess/Lawnstrings-Server).


---
## How to use:
Select `use this template -> create new repository`, name it with `<your_github_username>.github.io` (lower case every letter here),  and put your android translation into `raw/<game_version>` folder under `android_file.txt` name, result path should be `raw/<game_version>/android_file.txt`. For ios it will be `raw/<game_version>/ios_file.txt`. 
Push the changes, and you'll see 2 actions running on github, one after another. 
First one will create `gh-pages` branch, and there will be folders with such structure: `<game_version>/<ad>` and `<game_version/ios>`. 
If some of raw files weren't present, e.g., `raw/<game_version>/ios_file.txt`, then `<game_version/ios>` folder won't be created. 
These folders will contain two folders - `res_release` and `res_shipping`. All these directories will have `pvz2_l.txt` and `file_list.txt` files ready to use for your server-side pvz2c lawnstrings.

---
## How to actually make it appear in game? (Android-friendly edition)
You need to edit `serverconfig.rton` in `dynamic.rsb(.smf)` file of the game.
You need to grab it from the following path: `Android/data/com.popcap.<some package depeinding on store the game was downloaded from>/files`. 

Said rton is located in Packages, and you'll need to decrypt and decode it. 
I suggest [Sen](https://github.com/harumazzz/Sen.Environment) for that. 
After converting said file to json, find `LawnStringServerConfig` and replace corresponding links with your own ones.

Example links for 3.5.8 on android (on ios replace `ad` with `ios`):
```
https://<your_github_username>.github.io/3.5.8/ad/res_release
https://<your_github_username>.github.io/3.5.8/ad/res_shipping
```

After that, encrypt and encode json back to rton, pack `dynamic.rsb(.smf)` file back and put it into the game folder. 
But before - back up original `dynamic.rsb(.smf)` just in case. After that, launch your game, and you should see your translation here.

Most important steps will work even on ios, the only difference will be in rton location. 
I don't have any Apple device nor tools to work with it, so can't help much. But if you are doing that on ios, then you definitely know more than me) 
### Good luck with translation and enjoy the gaming!)