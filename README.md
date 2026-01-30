
### 💬 My Filters - additions (customize, edit or add more yourself)

<details>
  <summary align="center">YouTube Comments cleaner</summary>
  <br>[EasyList - Overview](<https://easylist.to/>)

```adblock
! ==================> YouTube Comments Cleaner | This removes those bot comments & More <==================
! Applies to main comments | (Add "\" before the "'" to make it apply: I\’m subbed) & Comment replies
youtube.com##ytd-page-manager ytd-watch-flexy #primary.ytd-watch-flexy #comment:has-text(/I\'m subbing | I\’m subbed|Buy ONE Get ONE FREE|use my code|Don\'t forget to visit|The sponsor|first purchase|Subscribe|Download/i):upward(ytd-comment-thread-renderer)
youtube.com##ytd-page-manager ytd-watch-flexy #primary.ytd-watch-flexy #replies ytd-comment-view-model:has(#author-text):has-text(/UTTP|NWO|UTube|Police|Troll|ZNTP|CABT|Joseph_14441|YFGA/)
! Only applies to replies of comments
youtube.com##ytd-page-manager ytd-watch-flexy #primary.ytd-watch-flexy ytd-comment-thread-renderer #expander-contents ytd-comment-view-model:has-text(/Here is new fu | Here is the fu | This is the clip | Finally it’s here | Finally Here is the fu | Telegram | Teleegram | I forgot to close the camera | LETS BE HONEST WE ALL REMEMBER | ТАР 0N MY РIC | I upload funny | read my name | Read My Profile | you will see it | Claim your prize | Link to the clip | MY CONTENT IS SO | Look at my banner | Lucky prize winners | IM SUBBING EVERYONE | DONT READ MY PROFILE | JJ said my music was fire on my page |first purchase|Don\'t translate| translate | My content is | are better than|Django|your dad|I WANT TO BE THE MOST|parents said if I hit|SI TNETNOC YM|oediv retteb ekam|retteb si tnetnoc ym|content is better|erutam era sdiK|UTTP|UT‎TP|RETTEB‎ YAW‎ SI‎ TNETNOC|erutam‎ era sdiK|IS WAY BETTER|IN MY SERVER|THERE IS A VIDEO|ailihp‎odep‎ ezila‎mroN|I AM WAY BETTER|CONTENT IS BETTER|videos‎ are‎ bet‎ter|naht retteb hcuM|RETTEB YAW ERA|AGFY|Tis a bot|shut up bot|in a video|Its finally completed|Read my name|youtu.be|I MADE A DISS TRACK|use my code|Hi guys|DO NOT REDEEM|WHY DID YOU REDEE|the chemical projection of signal stream/)
```

</details>


<details>
  <summary align="center">YouTube video remover (based on title text)</summary>
  <br>

```adblock
! Global AIO | Home page, Search page & Watching video recommended sidebar | ytd-video-renderer:has(#meta h3) = search results only? Idk.
youtube.com##ytd-page-manager :is(ytd-rich-item-renderer:has(#meta h3), ytd-compact-video-renderer:has(#video-title)):has-text(/Memes|GTA|Skyrim|Diablo|Fortnite/i)
```



<details>
  <summary align="center">YouTube thumbnail blurer - blurs if title contains: Spoiler, New Boss, Final Boss, Trailer, Teaser, Reveal & removes blur when hovered over</summary>
  <br>

```adblock
! ==========> YouTube Keywords blur thumbnail | Home Results, Watching video recommended sidebar & Search Results <==========
youtube.com##ytd-page-manager :is(ytd-rich-item-renderer:has(#meta h3), ytd-video-renderer:has(#meta h3), ytd-compact-video-renderer:has(#video-title)):has-text(/Spoiler|New Boss|Final Boss|Trailer|Teaser|Reveal/) ytd-thumbnail:not(:hover):style(filter: grayscale(100%) blur(8px) opacity(.1))
! ===> YouTube Keywords Whitelist | Add channels you wish to whitelist here <===
youtube.com##ytd-page-manager [class*="ytd-"] :is(#video-title-link, ytd-channel-name):has-text(/Minecraft|Kira/):upward(ytd-rich-item-renderer, ytd-video-renderer, ytd-compact-video-renderer):style(filter: none)
```

</details>

</details>

<details>
  <summary align="center">YouTube: removes new/useless animations... Oddly feels like it speeds up YouTube too</summary>
  <br>

```adblock
! Text animation, overlay animation, reactions, ads, player responses (like reactions, thumbs up, etc) & other stuff.... This oddly speed up YouTube | Use at on risk for now? Do more testing 28/06/24
! Prevent stats (such as likes and views) from live-updating
||youtube.com/youtubei/v1/updated_metadata
! Hide "smartimation" animations
youtube.com##yt-smartimation > :not(.smartimation__content)
youtube.com##yt-animated-action > :not(.animated-action__content-with-background)
youtube.com##:is(.smartimation__content, .animated-action__content-with-background) > :has(> lottie-component)
! Live reaction overlays
www.youtube.com##yt-reaction-control-panel-view-model
www.youtube.com##yt-reaction-control-panel-overlay-view-model
! ads, others / pointless updates
||music.youtube.com^$csp=worker-src 'none'
||www.youtube.com^$csp=worker-src 'none'
youtube.com##+js(json-prune, 2.playerResponse.adPlacements playerResponse.adPlacements playerResponse.playerAds adPlacements playerAds)
youtube.com##+js(json-prune, 2.playerResponse.adPlacements)
youtube.com##+js(json-prune, playerResponse.adPlacements)
youtube.com##+js(json-prune, playerResponse.playerAds)
youtube.com##+js(set, ytInitialPlayerResponse.adPlacements, null)
```

</details>

<details>
  <summary align="center">Steam review cleaners</summary>
  <br>

```adblock
! Steam Reviews Cleaner | This removes non English too... Add more if you find them
store.steampowered.com##.review_box:has-text(/因为这是|你要是真让|杀时间利器|差强人意| 好玩 优秀 |赞|目|Nobody reads the reviews anyways, so i'll just say i'm gay|Nobody will read my review, so I'll just say I'm gay|No one is going to read this comment so i'm just going to say that i'm gay|so I'll write that I'm gay|No ones gonna read this so I'm just gonna say it, I'm gay.|Got a cat here.|Here I will leave the cat|My buddy said that if I get|so I will write that I am gay|gay|I will leave the cat here|thumbs up and awards|Nobody will read my review|give it a thumbs up|will read this/i)
```

</details>


<details>
  <summary align="center">Reddit shenanigan</summary>
  <br>

```adblock
! Reddit Domain Cleaner | Should only clean your main page (I use Reddit Enhanced Suite instead of using this now)
! reddit.com##.listing-page.with-listing-chooser.loggedin .thing:has(.domain:has-text(/youtu.be|youtube|igorslab.de/i))

! Reddit - You can now drag and drop text when signed out... Bye bye lock
www.reddit.com##+js(aeld, mousedown, isSelectionOutOfRange)
www.reddit.com##+js(aeld, mouseup, shouldShowButton)

! Removes deleted comments + Filters remove botted comments by users
reddit.com##.commentarea .deleted .entry:has(.usertext.grayed)
reddit.com##.commentarea .entry:has-text(This post/comment has been automatically overwritten)

! Ublock Filter For Hiding "Blocked account" Comments
reddit.com##.Comment [id^="UserInfoTooltip"]>:not([data-testid="comment_author_link"]):upward(.Comment)
```

</details>




### 📜 Filter lists

**Possibly enabled**:
```
https://big.oisd.nl/
https://adaway.org/hosts.txt
https://hosts.anudeep.me/mirror/facebook.txt
https://www.i-dont-care-about-cookies.eu/abp
https://badblock.celenity.dev/abp/badblock.txt
https://malware-filter.gitlab.io/pup-filter/pup-filter.txt
https://hostfiles.frogeye.fr/firstparty-only-trackers-hosts.txt
https://raw.githubusercontent.com/badmojr/1Hosts/master/Lite/adblock.txt
https://raw.githubusercontent.com/fmhy/FMHYFilterlist/main/filterlist.txt
https://raw.githubusercontent.com/piperun/iploggerfilter/master/filterlist
https://cdn.jsdelivr.net/gh/hagezi/dns-blocklists@latest/adblock/pro.plus.txt
https://gitlab.com/hagezi/mirror/-/raw/main/dns-blocklists/adblock/tif.medium.txt
https://raw.githubusercontent.com/badmojr/1Hosts/refs/heads/master/Xtra/adblock.txt
https://raw.githubusercontent.com/nickspaargaren/no-google/master/pihole-google.txt
https://gitlab.com/hagezi/mirror/-/raw/main/dns-blocklists/adblock/ultimate.mini.txt
https://raw.githubusercontent.com/yokoffing/filterlists/refs/heads/main/click2load.txt
ttps://raw.githubusercontent.com/laylavish/uBlockOrigin-HUGE-AI-Blocklist/main/list.txt
https://raw.githubusercontent.com/yokoffing/filterlists/main/block_third_party_fonts.txt
https://raw.githubusercontent.com/DandelionSprout/adfilt/refs/heads/master/AnnoyancesList
https://raw.githubusercontent.com/yokoffing/filterlists/refs/heads/main/annoyance_list.txt
https://raw.githubusercontent.com/liamengland1/miscfilters/refs/heads/master/antipaywall.txt
https://raw.githubusercontent.com/DandelionSprout/adfilt/master/AdRemovalListForUnusualAds.txt
https://raw.githubusercontent.com/yokoffing/filterlists/refs/heads/main/privacy_essentials.txt
https://raw.githubusercontent.com/reek/anti-adblock-killer/master/anti-adblock-killer-filters.txt
https://raw.githubusercontent.com/DandelionSprout/adfilt/master/BrowseWebsitesWithoutLoggingIn.txt
https://raw.githubusercontent.com/LanikSJ/webannoyances/refs/heads/master/filters/web_annoyances.txt
https://raw.githubusercontent.com/LanikSJ/webannoyances/refs/heads/master/filters/floating_filters.txt
https://raw.githubusercontent.com/quenhus/uBlock-Origin-dev-filter/main/dist/all_search_engines/global.txt
https://gitflic.ru/project/magnolia1234/bypass-paywalls-clean-filters/blob/raw?file=bpc-paywall-filter.txt
https://raw.githubusercontent.com/DandelionSprout/adfilt/master/ClearURLs%20for%20uBo/clear_urls_uboified.txt
https://raw.githubusercontent.com/AdguardTeam/AdguardFilters/master/AnnoyancesFilter/Popups/sections/antiadblock.txt
```
**Disabled filter lists**:
```
https://easylist.to/easylist/easylist.txt
https://energized.pro/ultimate/adblock.txt
https://easylist.to/easylist/easyprivacy.txt
https://hosts.anudeep.me/mirror/adservers.txt
https://easylist.to/easylist/fanboy-social.txt
https://secure.fanboy.co.nz/fanboy-antifonts.txt
https://tgc.cloud/downloads/archive/hosts.alive.txt
https://secure.fanboy.co.nz/fanboy-cookiemonster.txt
https://secure.fanboy.co.nz/fanboy-annoyance_ubo.txt
https://filters.adtidy.org/extension/ublock/filters/14.txt
https://phishing.army/download/phishing_army_blocklist_extended.txt
https://raw.githubusercontent.com/arapurayil/aBL/main/filters/main.txt
https://raw.githubusercontent.com/fmhy/FMHYFilterlist/main/filterlist.txt
https://raw.githubusercontent.com/LanikSJ/webannoyances/master/ultralist.txt
https://raw.githubusercontent.com/hagezi/dns-blocklists/main/adblock/pro.txt
https://raw.githubusercontent.com/hagezi/dns-blocklists/main/hosts/multi.txt
https://raw.githubusercontent.com/hagezi/dns-blocklists/main/adblock/pro.plus.txt
https://raw.githubusercontent.com/mchangrh/yt-neuter/main/filters/sponsorblock.txt
https://raw.githubusercontent.com/yokoffing/filterlists/main/privacy_essentials.txt
https://raw.githubusercontent.com/hagezi/dns-blocklists/main/dnsmasq/native.apple.txt
https://raw.githubusercontent.com/hagezi/dns-blocklists/main/dnsmasq/native.tiktok.txt
https://raw.githubusercontent.com/Vran-n/uBlock-List/refs/heads/main/filters/modify%20twitter
https://raw.githubusercontent.com/DandelionSprout/adfilt/refs/heads/master/EmptyPaddingRemover.txt
https://raw.githubusercontent.com/deltabravozulu/pihole/refs/heads/main/frogeye_firstparty-trackers-hosts
https://raw.githubusercontent.com/DandelionSprout/adfilt/refs/heads/master/DeviantARTQualityArtMagnifier.txt
https://raw.githubusercontent.com/DandelionSprout/adfilt/refs/heads/master/YouTubeEvenMorePureVideoExperience.txt
```

📱 **Mobile Phone lists**:
```
https://badblock.celenity.dev/abp/android_whitelist.txt
https://gitlab.com/hagezi/mirror/-/raw/main/dns-blocklists/adblock/tif.medium.txt
https://raw.githubusercontent.com/misspent/uBlock-Origin-Information/refs/heads/main/uBo%20Filter%20list
https://raw.githubusercontent.com/DandelionSprout/adfilt/refs/heads/master/stayingonbrowser/Staying%20On%20The%20Phone%20Browser
https://raw.githubusercontent.com/DandelionSprout/adfilt/master/Alternate%20versions%20Anti-Malware%20List/AntiMalwareAdGuardHome.txt
```
[Main - Subscriptions | uBlacklist](<https://iorate.github.io/ublacklist/subscriptions>)  
[Super-SEO-Spam-Suppressor](<https://github.com/NotaInutilis/Super-SEO-Spam-Suppressor>)  
[SpamdexingSites](<https://github.com/elliotwutingfeng/SpamdexingSites>)  
[EasyList - Overview](<https://easylist.to/>)  
[Motherload of lists](<https://github.com/knapah/uBlockOrigin-Filterlist>)
⭐ [Energized Protection - block](<https://github.com/EnergizedProtection/block>)  
**Badblock** support whitelist for following:
```
- Android
- Apple
- Browser
- Captcha
- Captive
- Certificate Validation
- Click Tracking/Referral Domains
- GNU/Linux Whitelist
- Helpline
- LAN
- Microsoft
- Misc
- Mobile
- Mozilla
- Push Notifications
- Safe Browsing
- Time Servers
```



### ℹ️ Random Information

**YouTube**  
Blocking `jnn-pa.googleapis.com` completely destroys the loading of videos after a while of viewing them, making it so I have to refresh the page.  
`🔒 Privacy Essentials ` Import blocks the entry above, so use that at your own risk (as of: 24/07/2024)

