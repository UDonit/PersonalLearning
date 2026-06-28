# 绗竴璇?& 绗簩璇?鈥?闂瓟绮惧崕

> 鏈枃浠舵暣鐞嗕簡鏁欏杩囩▼涓敤鎴锋彁鍑虹殑鍏ㄩ儴闂涓庡搴旂殑娣卞叆鍥炵瓟銆傛寜涓婚鍒嗙粍锛屾柟渚垮悗闈㈡煡闃呫€?> 鎵€鏈夊洖绛斿潎鍩轰簬 Linux 鍐呮牳婧愮爜锛堜富绾跨増鏈級锛屽苟鏍囨敞浜嗗搴斿唴鏍告簮鐮佽矾寰勩€?
---

## 鐩綍

- [杞摼鎺ワ細涓轰粈涔堢洰鏍囦笉瀛樺湪涔熻兘鍒涘缓锛焆(#杞摼鎺ヤ负浠€涔堢洰鏍囦笉瀛樺湪涔熻兘鍒涘缓)
- [inode 鐨?lookup() 鎬庝箞宸ヤ綔锛熸墍鏈?inode 閮藉湪纾佺洏涓婂悧锛焆(#inode-鐨?lookup-鎬庝箞宸ヤ綔鎵€鏈?inode-閮藉湪纾佺洏涓婂悧)
- [rm 鍚?inode 鍜屾暟鎹粈涔堟椂鍊欓噴鏀撅紵"閲嶅惎"涓轰粈涔堟湁鏁堬紵](#rm-鍚?inode-鍜屾暟鎹粈涔堟椂鍊欓噴鏀鹃噸鍚负浠€涔堟湁鏁?
- [open() 璺緞瀛楃涓轰粈涔堣鎷疯礉鍒板唴鏍哥┖闂达紵](#open-璺緞瀛楃涓轰粈涔堣鎷疯礉鍒板唴鏍哥┖闂?
- [fs->pwd 鏄粈涔堬紵鎬庝箞鍒ゆ柇缁濆/鐩稿璺緞锛焆(#fs-pwd-鏄粈涔堟€庝箞鍒ゆ柇缁濆鐩稿璺緞)
- [鏍?dentry 涓轰粈涔堟案杩滀笉浼氳鎹㈠嚭锛焏cache 鑰佸寲瑙勫垯锛焆(#鏍?dentry-涓轰粈涔堟案杩滀笉浼氳鎹㈠嚭dcache-鑰佸寲瑙勫垯)
- [杞摼鎺ョ殑 inode 鏄€庝箞鎵惧埌鐨勶紵](#杞摼鎺ョ殑-inode-鏄€庝箞鎵惧埌鐨?
- [i_uid / i_gid 鏄?Linux 鑷繁瀹氫箟鐨勫苟鎸佷箙鍖栧埌纾佺洏鍚楋紵](#i_uid--i_gid-鏄?linux-鑷繁瀹氫箟鐨勫苟鎸佷箙鍖栧埌纾佺洏鍚?
- [涓轰粈涔?lookup_fast 鏈変袱涓紦瀛樿矾寰勶紙RCU + 甯﹂攣锛夋墠璧扮鐩?I/O锛焆(#涓轰粈涔?lookup_fast-鏈変袱涓紦瀛樿矾寰剅cu--甯﹂攣鎵嶈蛋纾佺洏-io)
- [璐熺紦瀛樹細涓嶄細杩囨湡锛熺綉缁滄枃浠剁郴缁燂紙NFS锛夋€庝箞鍔烇紵](#璐熺紦瀛樹細涓嶄細杩囨湡缃戠粶鏂囦欢绯荤粺nfs鎬庝箞鍔?
- [纭摼鎺ョ殑璇В锛氫负浠€涔堝湪 Git Bash 涓?inode 鍙蜂笉涓€鏍凤紵](#纭摼鎺ョ殑璇В涓轰粈涔堝湪-git-bash-涓?inode-鍙蜂笉涓€鏍?
- [纭摼鎺ユ槸鍚﹀垱寤轰簡鍙︿竴涓?inode锛焆(#纭摼鎺ユ槸鍚﹀垱寤轰簡鍙︿竴涓?inode)
- [dcache 鐨勮礋缂撳瓨浼氳澶ч噺鏃犳晥鏌ヨ姹℃煋鍚楋紵](#dcache-鐨勮礋缂撳瓨浼氳澶ч噺鏃犳晥鏌ヨ姹℃煋鍚?
- [lookup_fast 涓煡鎵?dcache 鏄爲鏌ユ壘鍚楋紵](#lookup_fast-涓煡鎵?dcache-鏄爲鏌ユ壘鍚?
- [鎵撳紑澶氬眰璺緞鐨勬祦绋嬫槸灞傚眰閫掕繘鐨勶紵](#鎵撳紑澶氬眰璺緞鐨勬祦绋嬫槸灞傚眰閫掕繘鐨?
- [dentry 瀛樺湪鏃跺唴鏍告槸鍚︿繚璇?inode 涓€瀹氬瓨鍦紵](#dentry-瀛樺湪鏃跺唴鏍告槸鍚︿繚璇?inode-涓€瀹氬瓨鍦?
- [ext2/ext3 鐨?inode 瀛樺偍鍦ㄥ摢閲岋紵](#ext2ext3-鐨?inode-瀛樺偍鍦ㄥ摢閲?
- [dcache 鐨勮璁℃剰鍥炬槸浠€涔堬紵](#dcache-鐨勮璁℃剰鍥炬槸浠€涔?

---

## 杞摼鎺ワ細涓轰粈涔堢洰鏍囦笉瀛樺湪涔熻兘鍒涘缓锛?
**鍒涘缓鏃朵笉鍋氱洰鏍囨鏌ャ€?* 鍐呮牳鍙仛涓€浠朵簨鈥斺€旀妸鐩爣璺緞褰撳瓧绗︿覆鍐欏叆杞摼鎺ユ枃浠剁殑鏁版嵁鍧椼€?
```
ln -s /nonexistent/path link
  鈫?symlink("/nonexistent/path", "link") 绯荤粺璋冪敤
    鈫?VFS 鍒涘缓涓€涓被鍨嬩负 S_IFLNK 鐨?inode
    鈫?鏂囦欢鍐呭灏辨槸瀛楃涓?"/nonexistent/path"
    鈫?杩斿洖鎴愬姛 鉁?```

鐩村埌浣犺闂畠锛堝 `cat link`锛夛紝VFS 瑙ｆ瀽璺緞鏃跺彂鐜?inode 绫诲瀷鏄?`S_IFLNK`锛屾墠璋冪敤 `dentry->d_inode->i_op->follow_link()` 璇昏蒋閾炬帴鍐呭锛岀劧鍚?*閲嶆柊鍙戣捣 lookup()**銆傝繖鏃跺€欑洰鏍囦笉瀛樺湪鎵嶆姤閿欍€?
**璁捐鍘熷垯**锛氬垱寤烘椂涓嶈В鏋愶紙lazy锛夛紝浣跨敤鏃舵墠瑙ｆ瀽锛坥n-demand锛夈€傝繖涔熸槸杞摼鎺ュ彲浠ヨ法鏂囦欢绯荤粺鐨勫師鍥犫€斺€斿畠瀛樼殑鏄?璺緞瀛楃涓?锛屼笉鏄?inode 鍙枫€?
---

## inode 鐨?lookup() 鎬庝箞宸ヤ綔锛熸墍鏈?inode 閮藉湪纾佺洏涓婂悧锛?
瀵逛簬 ext4 杩欑被纾佺洏鏂囦欢绯荤粺锛屾渶缁堟槸浠?inode 琛ㄨ鍙栥€備絾瀹屾暣璺緞鏄細

```
lookup("/home/user/doc.txt")
  鈹?  鈹溾攢 1. 妫€鏌?dcache锛堝唴瀛樹腑鐨?dentry 缂撳瓨锛?  鈹?    鍛戒腑 鈫?鐩存帴杩斿洖锛坕node 鍙兘鍦紝涔熷彲鑳借鎹㈠嚭浜嗭級
  鈹?  鈹溾攢 2. dcache 鏈懡涓?鈫?鐖剁洰褰?inode 鐨?i_op->lookup()
  鈹?    鈹溾攢 ext4: ext4_lookup() 鈫?ext4_iget() 鈫?__ext4_iget()
  鈹?    鈹?        鈫?浠庣鐩?inode 琛ㄨ鍙?inode 鏁版嵁 鈫?濉厖 struct inode
  鈹?    鈹?  鈹?    鈹斺攢 procfs: proc_lookup() 鈫?proc_pid_lookup()
  鈹?                鈫?浠?task_struct 鐢熸垚 inode锛堜笉纰扮鐩橈紒锛?  鈹?  鈹斺攢 3. 鏂板缓 dentry锛屾寕鍏?dcache锛屾寚鍚戝姞杞藉ソ鐨?inode
```

**鍏抽敭鐐?*锛歭ookup() 鏄竴涓?VFS 鎺ュ彛锛堝嚱鏁版寚閽堬級锛屾瘡涓枃浠剁郴缁熻嚜宸卞疄鐜般€?鎵€鏈?inode 閮藉湪纭洏鏈夊浠?鍙€傜敤浜庣鐩樻枃浠剁郴缁熴€俻rocfs 绛夎櫄鎷熸枃浠剁郴缁熺殑 inode 鍙湪鍐呭瓨涓瓨鍦紝閲嶅惎灏辨病浜嗐€?
---

## rm 鍚?inode 鍜屾暟鎹粈涔堟椂鍊欓噴鏀撅紵"閲嶅惎"涓轰粈涔堟湁鏁堬紵

浠庡弻寮曠敤璁℃暟妯″瀷鐞嗚В锛?
```
inode 閲婃斁鏉′欢 = (i_nlink == 0) 涓?(i_count == 0)
                  鈫?纾佺洏涓婃病浜鸿     鈫?鍐呭瓨涓病浜虹敤
```

| 璁℃暟 | 绫诲瀷 | 璁板綍浠€涔?| 璋佹搷浣?|
|------|------|---------|--------|
| **i_nlink** | 纾佺洏绾у埆 | 鏈夊灏戜釜鐩綍椤规寚鍚戣繖涓?inode | `vfs_link()` +1, `vfs_unlink()` -1 |
| **i_count** | 鍐呭瓨绾у埆 | 鏈夊灏戜釜鍐呮牳瀵硅薄姝ｅ湪浣跨敤杩欎釜 inode | `d_add()` +1, `iput()` -1 |

**rm 鐩稿綋浜?unlink()**锛岃 i_nlink 鍑?1銆備絾濡傛灉杩樻湁杩涚▼鎵撳紑浜嗚繖涓枃浠讹紙鎸佹湁 fd 鈫?file 鈫?inode 寮曠敤锛夛紝i_count > 0锛宨node 鍜屾暟鎹潡涓嶄細閲婃斁銆傜瓑 close() 鍚?i_count 褰掗浂鎵嶇湡姝ｉ噴鏀俱€?
**"閲嶅惎涓轰粈涔堣兘閲婃斁"**锛氶噸鍚悗鎵€鏈夎繘绋嬬粓姝?鈫?鎵€鏈?fd 琚叧闂?鈫?i_count 褰掗浂 鈫?inode 鍜屽搴旀暟鎹潡琚洖鏀躲€傛妧鏈笂娌￠敊锛屼絾鍦ㄦ甯歌繍缁翠腑涓嶆槸鎺ㄨ崘鎵嬫鈥斺€旀洿濂界殑鍋氭硶鏄?`kill -HUP` 璁╄繘绋嬮噸鏂版墦寮€鏃ュ織鏂囦欢銆?
鏃堕棿绾挎帹婕旓細

```
鍒濆鐘舵€侊細/tmp/test.txt 鈫?inode #42 [i_nlink=1, i_count=0]

open()          鈫?dentry 鍒涘缓 鈫?d_add()
                鈫?[i_nlink=1, i_count=1]  鈫?dentry 閽変綇浜?inode

ln /tmp/hard.txt 鈫?绗簩涓?dentry 鈫?d_add()
                鈫?[i_nlink=2, i_count=2]

rm /tmp/test.txt 鈫?vfs_unlink() 鈫?[i_nlink=1, i_count=1]
                鈫?dentry 宸茶鎽橀櫎浣?inode 杩樺湪锛堟湁纭摼鎺ワ級

rm /tmp/hard.txt
                鈫?vfs_unlink() 鈫?[i_nlink=0, i_count=0]
                鈫?evict() 閲婃斁 inode 鉁?```

---

## open() 璺緞瀛楃涓轰粈涔堣鎷疯礉鍒板唴鏍哥┖闂达紵

涓嶆槸"鏀惧埌鏍堥噷"杩欎箞绠€鍗曪紝鑰屾槸**瀹夊叏锛堥槻 TOCTOU锛? 闅旂锛堜笉鍚屽湴鍧€绌洪棿锛? 澶嶇敤锛堝紩鐢ㄨ鏁帮級** 涓夌榻愪笅銆?
### 鈶?瀹夊叏闅旂鈥斺€擳OCTOU 婕忔礊

```c
// 鐢ㄦ埛鎬佺▼搴?char *path = "doc.txt\0";
fd = open(path, O_RDONLY);   // 鈶?绯荤粺璋冪敤锛屽唴鏍稿紑濮嬭В鏋?
// 涓庢鍚屾椂锛屽彟涓€涓嚎绋嬶細
// path[0] = '\0';            // 鈶?璺緞鍙樻垚浜嗙┖瀛楃涓?```

濡傛灉鍐呮牳鐩存帴浣跨敤鐢ㄦ埛鎬佺殑鎸囬拡锛屽湪 `copy_from_user()` 鍒?`link_path_walk()` 涔嬮棿锛岀敤鎴锋€佸彲浠ュ湪鍙︿竴涓嚎绋嬩慨鏀硅矾寰勫瓧绗︿覆鍐呭銆傝繖灏辨槸 **TOCTOU锛圱ime-of-Check-to-Time-of-Use锛夊畨鍏ㄦ紡娲?*銆?
鍐呮牳鐨勮В鍐虫柟妗堬細

```c
// fs/open.c
long do_sys_open(const char __user *filename, int flags, umode_t mode)
{
    char *tmp = getname(filename);       // copy_from_user()
    fd = do_filp_open(tmp, flags);       // 瑙ｆ瀽鐨勬槸鍐呮牳绌洪棿鐨勫壇鏈?    putname(tmp);
    return fd;
}
```

鎷疯礉瀹屾垚鍚庤矾寰勫氨鍦ㄥ唴鏍告爤涓婏紝鐢ㄦ埛鎬佸啀涔熸棤娉曚慨鏀广€?
### 鈶?鍦板潃绌洪棿闅旂
鐢ㄦ埛鎬佸拰鍐呮牳鎬佷娇鐢ㄤ笉鍚岀殑椤佃〃锛圫MAP/SMEP 淇濇姢锛夈€傚唴鏍镐笉鑳界洿鎺ヨВ寮曠敤鐢ㄦ埛鎬佹寚閽堚€斺€旈渶瑕侀€氳繃 `copy_from_user()` / `copy_to_user()`锛岃繖浜涘嚱鏁颁細妫€鏌ュ湴鍧€鑼冨洿銆佸鐞嗙己椤靛紓甯搞€?
### 鈶?寮曠敤璁℃暟澶嶇敤
`getname()` 杩斿洖鐨?`struct filename *` 甯﹀紩鐢ㄨ鏁扳€斺€斿涓嚎绋嬪悓鏃?open() 鍚屼竴涓矾寰勫瓧绗︿覆鏃讹紝鍙互澶嶇敤鍚屼竴涓壇鏈€?
---

## fs->pwd 鏄粈涔堬紵鎬庝箞鍒ゆ柇缁濆/鐩稿璺緞锛?
`fs` 鏄?`current->fs`锛屾寚鍚?`struct fs_struct`锛屽瓨鍌ㄥ湪杩涚▼鐨?`task_struct` 涓€備笉鏄嚱鏁版寚閽堛€?
```c
// include/linux/fs_struct.h
struct fs_struct {
    struct path    root;       // 杩涚▼鏍圭洰褰?    struct path    pwd;        // 杩涚▼褰撳墠宸ヤ綔鐩綍
    struct path    home;       // home 鐩綍
    rwlock_t       lock;
    int            users;
};

// struct path = vfsmount + dentry
struct path {
    struct vfsmount *mnt;   // 鎸傝浇淇℃伅
    struct dentry   *dentry; // 瀵瑰簲鐨?dentry
};
```

**鍒ゆ柇缁濆/鐩稿璺緞**锛氬氨鏄湅璺緞瀛楃涓茬殑绗竴涓瓧绗︽槸涓嶆槸 `'/'`銆?
```c
// fs/namei.c 鈥?link_path_walk()
if (name[0] == '/') {
    nd->path = current->fs->root;  // 浠庢牴鐩綍寮€濮?} else {
    nd->path = current->fs->pwd;   // 浠庡綋鍓嶅伐浣滅洰褰曞紑濮?}
```

---

## 鏍?dentry 涓轰粈涔堟案杩滀笉浼氳鎹㈠嚭锛焏cache 鑰佸寲瑙勫垯锛?
鏍?dentry 鐨?d_count 琚?*姘镐箙鎬у湴鎸佹湁澶氫釜寮曠敤**锛屾案杩滀笉浼氶檷鍒?0锛?
```
寮曠敤鏉ユ簮锛?1. super_block->s_root 鎸佹湁涓€涓紩鐢紙鍙鏂囦欢绯荤粺鎸傝浇鐫€锛?2. 姣忎釜杩涚▼鐨?fs->root.dentry 鎸佹湁涓€涓紩鐢?3. mount 缁撴瀯鎸佹湁寮曠敤
鈫?d_count 姘歌繙 > 0锛屼笉浼氳 LRU 鍥炴敹閫変腑
```

### dcache 鍥炴敹浼樺厛绾ц〃

| 浼樺厛绾?| 绫诲瀷 | 鏉′欢 |
|--------|------|------|
| 馃 鏈€楂?| 璐?dentry | d_inode == NULL |
| 馃 | 鏈娇鐢ㄧ殑姝?dentry | d_count == 0锛屼笖鏈€杩戞湭琚闂?|
| 馃 | 鏈€杩戣璁块棶鐨勬 dentry | 鍒氱敤杩囷紝绉诲埌 LRU 灏鹃儴淇濅竴涓?|
| 鉂?姘镐笉 | 鏍?dentry + pin浣?| d_count > 0 鎴?dentry->d_parent == dentry |

### 瀹屾暣鍥炴敹娴佺▼

```
鍐呭瓨鍘嬪姏鍒版潵
  鈫?kswapd / direct reclaim 婵€娲?    鈫?shrink_slab() 琚皟鐢?      鈫?super_cache_scan() 鈫?prune_dcache_sb()
        鈫?dentry_lru_isolate() 閫愪釜鍒ゆ柇锛?          鈹斺攢 d_count > 0锛熲啋 璺宠繃
          鈹斺攢 d_inode == NULL锛熲啋 绔嬪嵆鍥炴敹 馃
          鈹斺攢 鏈繃鏈燂紵鈫?绉诲埌 LRU 灏鹃儴鍐嶇瓑绛夛紙榛樿 45 绉掕繃鏈燂級
          鈹斺攢 杩囨湡浜?鈫?鍥炴敹
```

`dcache_age_limit` 榛樿 45 绉掞紝閫氳繃 `/proc/sys/fs/dentry-state` 鍙娴嬨€?
---

## 杞摼鎺ョ殑 inode 鏄€庝箞鎵惧埌鐨勶紵

**涓嶆槸閫氳繃鐖剁洰褰?lookup 鎵惧埌鐨勩€?* 鍒嗕袱涓樁娈碉細

**绗竴闃舵**锛氶€愬眰瑙ｆ瀽璺緞鎵惧埌杞摼鎺ユ湰韬?
```
"/home/user/link_to_doc.txt"
  鈫?"/" 鈫?"home" 鈫?"user" 鈫?"link_to_doc.txt"
                                                 鈫?                            鐖剁洰褰?"user" 鐨?i_op->lookup() 鏌ュ埌
                            杩斿洖 dentry 鍜?inode
                            妫€鏌?i_mode 鈫?绫诲瀷鏄?S_IFLNK锛?```

**绗簩闃舵**锛氳鍙栬蒋閾炬帴鍐呭锛屼綔涓烘柊璺緞閲嶆柊瑙ｆ瀽

```c
// fs/namei.c 鈥?pick_link()
const char *target = inode->i_link;  // 鐭摼鎺?<60B)瀛樺湪 i_block 涓?    // 鎴?target = i_op->get_link(dentry, inode, &done);  // 闀块摼鎺ヨ鏁版嵁鍧?
// 鐒跺悗鎶?target 璁句负寰呰В鏋愯矾寰勶紝鍥炲埌 link_path_walk() 閲嶆柊瑙ｆ瀽
```

**鐭蒋閾炬帴鐨?inline data 浼樺寲**锛歟xt4 鐨?inode 澶у皬浠?128B锛坋xt2/3锛夋墿灞曞埌 256B锛坋xt4锛夛紝澶氬嚭鏉ョ殑绌洪棿瓒充互瀛樻斁寰堢煭鐨勬枃浠舵暟鎹€傚浜?< 60 瀛楄妭鐨勮蒋閾炬帴锛岀洰鏍囧瓧绗︿覆鐩存帴瀛樺湪 struct inode 鐨?i_block[] 鏁扮粍涓紝杩為澶栫殑鏁版嵁鍧楅兘涓嶉渶瑕佸垎閰嶃€?
---

## i_uid / i_gid 鏄?Linux 鑷繁瀹氫箟鐨勫苟鎸佷箙鍖栧埌纾佺洏鍚楋紵

**鏄€傚啓鍏ョ鐩樼殑 inode 琛ㄣ€?*

```c
// ext4 纾佺洏涓婄殑 inode 缁撴瀯
struct ext4_inode {
    __le16  i_mode;        // 鏂囦欢绫诲瀷 + 鏉冮檺浣?    __le16  i_uid;         // 浣?16 浣?UID  鈫?鍐欏叆纾佺洏 鉁?    __le32  i_size_lo;
    __le32  i_atime;       // 璁块棶鏃堕棿
    __le32  i_ctime;       // 鍒涘缓鏃堕棿
    __le32  i_mtime;       // 淇敼鏃堕棿
    __le32  i_dtime;       // 鍒犻櫎鏃堕棿
    __le16  i_gid;         // 浣?16 浣?GID  鈫?鍐欏叆纾佺洏 鉁?    // ...
};
```

鍐呭瓨涓殑 `struct inode` 鍔犺浇鑷鐩橈細

```c
// fs/ext4/inode.c 鈥?ext4_iget()
inode->i_uid  = raw_inode->i_uid;   // 浠庣鐩樺姞杞?inode->i_gid  = raw_inode->i_gid;   // 浠庣鐩樺姞杞?```

淇敼锛堝 `chown`锛夊悗锛宍mark_inode_dirty()` 鏍囪涓鸿剰锛宖lusher 绾跨▼寮傛鍐欏洖纾佺洏銆?
### 涓嶅悓鏂囦欢绯荤粺鐨?UID 瀛樺偍宸紓

| 鏂囦欢绯荤粺 | UID 瀛樺偍鏂瑰紡 |
|---------|------------|
| ext4 | inode 琛ㄤ腑鐨勫浐瀹氬瓧娈碉紙16 浣?+ 楂?16 浣嶆墿灞曪級 |
| NTFS | $FILE_NAME 灞炴€у拰 $SECURITY_DESCRIPTOR 涓殑 SID |
| FAT32 | 娌℃湁 UID 姒傚康锛屾墍鏈夋枃浠舵樉绀轰负 root |
| exFAT | 娌℃湁 UID 姒傚康 |

杩欏氨鏄负浠€涔堜粠 FAT32 U 鐩樻嫹鏂囦欢鍥炴潵 owner 閮芥槸 root鈥斺€斿洜涓?FAT 鏍煎紡鏍规湰娌℃湁 i_uid 瀛楁銆俶ount 鏃堕€氳繃鍙傛暟鎸囧畾锛?
```bash
mount -o uid=1000,gid=1000 /dev/sdb1 /mnt/usb
```

---

## 涓轰粈涔?lookup_fast 鏈変袱涓紦瀛樿矾寰勶紙RCU + 甯﹂攣锛夋墠璧扮鐩?I/O锛?
涓や釜璺緞鏌ョ殑鏄?*鍚屼竴涓搱甯岃〃**銆傚叧绯绘槸**涔愯閿佸畾 vs 鎮茶閿佸畾**銆?
### RCU 璺緞锛坃_d_lookup_rcu()锛夊け璐ョ殑鍘熷洜

鍗充娇 dentry 鍦ㄥ搱甯岃〃涓紝RCU 璺緞涔熷彲鑳借繑鍥?NULL锛?
| 澶辫触鍘熷洜 | 鍦烘櫙 | 棰戠巼 |
|---------|------|------|
| **seqcount 楠岃瘉澶辫触** | RCU 璇荤殑杩囩▼涓彟涓€涓?CPU 淇敼浜?dentry锛宻eq 鍙樹簡锛屼涪寮冪粨鏋?| 甯歌 |
| **d_inode 涓?NULL** | 姝ｈ d_delete() 鎽橀櫎杩囩▼涓?| 杈冨皯 |
| **RCU 涓寸晫鍖轰笉鑳?sleep** | 闇€鍋?I/O 閲嶉獙璇佺殑鏂囦欢绯荤粺锛堝 NFS锛夌洿鎺ユ斁寮?| 鐗瑰畾鍦烘櫙 |

### 涓夎矾寰勫畬鏁撮€昏緫

```
lookup_fast()
   鈹?   鈹溾攢 __d_lookup_rcu() 鈫?鍛戒腑 鈫?success 鉁咃紙鏈€棰戠箒锛?   鈹?   澶辫触锛坰eq 鍙樹簡 / 骞跺彂鍐?/ 闇€瑕?sleep锛?   鈹?   鈫?   鈹溾攢 __d_lookup() 鈫?鍛戒腑 鈫?success 鉁咃紙鎸侀攣閲嶈瘯锛?   鈹?   澶辫触锛堢湡鐨勬病鏈?dentry / inode 宸查噴鏀撅級
   鈹?   鈫?   鈹斺攢 lookup_slow() 鈫?纾佺洏 I/O 鉂?```

**RCU 璺緞**鍥炵瓟鐨勬槸"鎴戞病鐪嬪埌鏈変汉鍔ㄥ畠锛岃繖涓粨鏋滃彲淇?銆?*甯﹂攣璺緞**鍥炵瓟鐨勬槸"鎴戠幇鍦ㄥ氨瑕佷竴涓‘瀹氱殑缁撴灉锛岀瓑涔熻绛夊埌"銆?
---

## 璐熺紦瀛樹細涓嶄細杩囨湡锛熺綉缁滄枃浠剁郴缁燂紙NFS锛夋€庝箞鍔烇紵

### 鏈湴鏂囦欢绯荤粺锛坋xt4/XFS锛変笉浼氳繃鏈?
鎵€鏈夋枃浠舵搷浣滅粡杩囧悓涓€涓唴鏍革紝鍒涘缓鏂囦欢鏃惰嚜鍔ㄨ浆姝ｈ礋 dentry锛?
```c
// vfs_create() 鈫?鍒涘缓鏂囦欢
// 鈫?d_instantiate(dentry, inode)
// 鈫?dentry->d_inode 浠?NULL 鍙樻垚鏈夋晥 inode
// 鈫?鍚屼竴涓?dentry 浠庤礋鍙樻 鉁?```

### NFS 纭疄浼氾紒

```
鏈哄櫒 A锛歴tat("/shared/file") 鈫?涓嶅瓨鍦?鈫?NFS client 缂撳瓨璐?dentry
鏈哄櫒 B锛歟cho "hello" > /shared/file   鈫?鏂囦欢琚垱寤猴紙鏈嶅姟鍣ㄤ笂锛?鏈哄櫒 A锛歴tat("/shared/file") 鈫?璐?dentry 鍛戒腑 鈫?杩斿洖"涓嶅瓨鍦? 鈫?鉂?```

NFS 鐨勮В鍐虫柟妗堚€斺€擿d_revalidate()` 鍥炶皟锛?
```c
// fs/nfs/dir.c
static const struct dentry_operations nfs_dentry_operations = {
    .d_revalidate = nfs_lookup_revalidate,  // 姣忔 lookup 楠岃瘉鏈夋晥鎬?};

// lookup_fast() 涓鏌?DCACHE_OP_REVALIDATE 鏍囧織
// 濡傛灉鏈?鈫?璋冪敤 d_revalidate()
// NFS 鐨勫疄鐜?鈫?鍙戦€?NFS LOOKUP RPC 鍒版湇鍔″櫒纭
```

**娉ㄦ剰**锛歊CU 璺緞涓嬩笉鑳藉仛 I/O锛屾墍浠?NFS 鐨?d_revalidate 鍦?RCU 璺緞涓繑鍥?`-ECHILD`锛岃 VFS 閫€鍒版參閫熻矾寰勫啀鍋氶獙璇併€?
### 涓嶅悓鏂囦欢绯荤粺鐨勮礋缂撳瓨绛栫暐

| 鏂囦欢绯荤粺 | 璐熺紦瀛樻湁鏁堟€?| 鍘熷洜 |
|---------|------------|------|
| ext4/XFS/btrfs | 鉁?姘镐笉杩囨湡 | 鍚屼竴鍐呮牳绠＄悊鎵€鏈夋搷浣?|
| NFS锛堥粯璁わ級 | 鉂?闇€瑕佹瘡娆￠獙璇?| 鍏朵粬瀹㈡埛绔彲鑳藉湪鏈嶅姟鍣ㄤ笂鎿嶄綔 |
| NFS锛坅creg 鍙傛暟锛?| 鈿狅笍 绐楀彛鍐呮湁鏁?| `acregmin/acregmax` 鎺у埗楠岃瘉闂撮殧 |
| FUSE | 鍙栧喅浜庡疄鐜?| 鑷畾涔?d_revalidate 琛屼负 |

---

## 纭摼鎺ョ殑璇В锛氫负浠€涔堝湪 Git Bash 涓?inode 鍙蜂笉涓€鏍凤紵

**Git Bash 鐨?`ln` 琚槧灏勬垚浜嗘枃浠跺鍒讹紝涓嶆槸鐪熸鐨勭‖閾炬帴銆?*

鍦ㄧ湡姝ｇ殑 Linux 涓婏細

```bash
$ touch test.txt
$ ln test.txt link.txt
$ ls -li test.txt link.txt
1065432 -rw-r--r-- 2 user user 0 Jun 23 10:00 test.txt
1065432 -rw-r--r-- 2 user user 0 Jun 23 10:00 link.txt  鈫?涓€妯′竴鏍凤紒
```

DNS 妫€鏌ワ紙Docker 蹇€熼獙璇侊級锛?
```bash
docker run --rm -it alpine sh -c "
  touch test.txt && echo 'hello world' > test.txt
  ln test.txt hard.txt && ln -s test.txt soft.txt
  echo '=== 纭摼鎺?===' && ls -li test.txt hard.txt
  echo '=== 杞摼鎺?===' && ls -li test.txt soft.txt
  echo '=== 鍒犲師鏂囦欢鍚?===' && rm test.txt
  echo '纭摼鎺?' && cat hard.txt 2>&1 || echo '澶辫触'
  echo '杞摼鎺?' && cat soft.txt 2>&1 || echo '澶辫触'
"
```

---

## 纭摼鎺ユ槸鍚﹀垱寤轰簡鍙︿竴涓?inode锛?
**娌℃湁銆?* 纭摼鎺ユ槸鍒涘缓涓€涓柊鐨?dentry锛屾寚鍚?*宸叉湁鐨?inode**锛岀劧鍚庢妸 inode 鐨?`i_nlink` 鍔?1銆?
```c
// fs/namei.c 鈥?vfs_link()
new_dentry->d_inode = old_dentry->d_inode;  // 鎸囧悜鍚屼竴涓?inode
inode->i_nlink++;                            // 閾炬帴璁℃暟 +1
```

| 鎿嶄綔 | inode 鍙?| i_nlink | 鏁版嵁鍧?|
|------|----------|---------|--------|
| `cp a.txt b.txt` | 鉂?涓嶅悓 | 鍚?1锛堢嫭绔嬶級 | 涓や唤鐙珛鍓湰 |
| `ln a.txt b.txt`锛堢‖閾炬帴锛?| 鉁?鐩稿悓 | 浠?1鈫? | 鍏变韩鍚屼竴浠芥暟鎹?|
| `ln -s a.txt b.txt`锛堣蒋閾炬帴锛?| 鉂?涓嶅悓 | 鏂?inode 鐙珛 | b.txt 瀛樼殑鏄瓧绗︿覆 "a.txt" |

---

## dcache 鐨勮礋缂撳瓨浼氳澶ч噺鏃犳晥鏌ヨ姹℃煋鍚楋紵

**浼氥€傝繖鏄竴涓湡瀹炲瓨鍦ㄧ殑鏀诲嚮闈€?*

```c
// 鎭舵剰绋嬪簭
for (i = 0; ; i++) {
    sprintf(path, "/usr/share/icons/%d.png", i);
    open(path, O_RDONLY);  // 鍑犱箮閮戒笉瀛樺湪
}
```

鍐呮牳鐨勯槻寰℃墜娈碉細

| 闃插尽 | 鏈哄埗 | 鏁堟灉 |
|------|------|------|
| LRU 浼樺厛鍥炴敹璐?dentry | `dentry_lru_isolate()` 浼樺厛閫夋嫨 `d_inode==NULL` 鐨?| 鉁?鏈夋晥 |
| 绯荤粺鍐呭瓨鍥炴敹 | 閫氳繃 shrink_slab() 鏁翠綋缂╂按 | 鉁?闂存帴淇濇姢 |
| 鏃犵‖涓婇檺 | `/proc/sys/fs/dentry-state` 鍙娴?| 鈿狅笍 杞檺鍒?|

鐪熷疄妗堜緥锛欳VE-2018-5390锛圫egmentSmack锛夊埄鐢ㄥぇ閲忕暩褰?TCP 鍖呰Е鍙戝唴鏍歌矾寰勮В鏋愶紝浜х敓澶ч噺璐?dentry銆傚悗缁唴鏍稿鍔犱簡鏇存縺杩涚殑璐?dentry 鍥炴敹閫昏緫銆?
---

## lookup_fast 涓煡鎵?dcache 鏄爲鏌ユ壘鍚楋紵

**涓嶆槸銆傛槸鍝堝笇琛ㄦ煡鎵俱€?*

```c
#define D_HASH_BITS  15
static struct hlist_bl_head dentry_hashtable[1 << D_HASH_BITS];  // 32768 涓《
```

鍝堝笇閿?= `hash(parent_dentry_ptr + d_name.string)`

dentry 鍦ㄩ€昏緫涓婄粍鎴愭爲锛堥€氳繃 d_parent銆乨_subdirs 鎸囬拡缁存姢瀛愭爲鍏崇郴锛夛紝浣嗘煡鎵惧叆鍙ｆ槸鍝堝笇琛ㄢ€斺€?*O(1) 鏃堕棿澶嶆潅搴?*銆俤entry 闂寸殑"鏍?鐢ㄤ簬鐩綍閫掑綊鍒犻櫎绛夐亶鍘嗗満鏅紝涓嶇敤浜庢煡鎵俱€?
---

## 鎵撳紑澶氬眰璺緞鐨勬祦绋嬫槸灞傚眰閫掕繘鐨勶紵

**瀹屽叏姝ｇ‘銆?* 绗竴娆¤闂?`open("/home/user/project/doc.txt")`锛?
```
绗?灞傦細瑙ｆ瀽 "home"  鈫?dcache 鏈懡涓?鈫?璇荤鐩樼洰褰曟枃浠?鈫?鍔犺浇 inode 鈫?鍒涘缓 dentry
绗?灞傦細瑙ｆ瀽 "user"  鈫?dcache 鏈懡涓?鈫?璇荤鐩樼洰褰曟枃浠?鈫?鍔犺浇 inode 鈫?鍒涘缓 dentry
绗?灞傦細瑙ｆ瀽 "project" 鈫?dcache 鏈懡涓?鈫?璇荤鐩樼洰褰曟枃浠?鈫?鍔犺浇 inode 鈫?鍒涘缓 dentry
绗?灞傦細瑙ｆ瀽 "doc.txt" 鈫?dcache 鏈懡涓?鈫?璇荤鐩樼洰褰曟枃浠?鈫?鍔犺浇 inode 鈫?鍒涘缓 dentry
鈫?4 娆＄鐩?I/O銆傛瘡灞傞兘璧颁簡瀹屾暣璺緞銆?
绗簩娆¤闂悓涓€涓矾寰勶細
鈫?鎵€鏈?dentry 閮藉湪 dcache 涓?鈫?4 娆?lookup_fast鈫掑叏閮ㄥ懡涓?鈫?0 娆＄鐩?I/O銆?```

濡傛灉涓棿鏌愬眰鐨?dentry 琚?LRU 鍥炴敹浜嗭紙姣斿 "project" 琚洖鏀讹紝浣?"home" 鍜?"user" 杩樺湪锛夆啋 浠庤鍥炴敹鐨勯偅涓€灞傚紑濮嬮噸鏂拌蛋纾佺洏 I/O锛?閮ㄥ垎缂撳瓨"锛夈€?
---

## dentry 瀛樺湪鏃跺唴鏍告槸鍚︿繚璇?inode 涓€瀹氬瓨鍦紵

**缁濆淇濊瘉銆?* 鎷呬繚鏈哄埗鏄?dentry 瀵?inode 鎸佹湁寮曠敤璁℃暟銆?
```c
// fs/dcache.c 鈥?d_add()
void d_add(struct dentry *dentry, struct inode *inode)
{
    dentry->d_inode = inode;
    if (inode) {
        atomic_inc(&inode->i_count);  // 鈫?dentry 閽変綇浜?inode
    }
    d_rehash(dentry);  // 鎸傚叆鍝堝笇琛紝鍙 lookup 鎵惧埌
}
```

鎷呬繚閾撅細

```
dentry 鍦ㄥ搱甯岃〃涓?鈫?dentry->d_inode != NULL 鈫?inode->i_count >= 1 鈫?inode 涓嶄細琚?evict
```

### 鍒犻櫎鎿嶄綔鐨?姝ｇ‘鎬?

```
rm test.txt 涔嬪墠锛?  dentry "test.txt" 鈹€鈹€閽変綇鈹€鈹€鈫?inode [i_nlink=1, i_count=1]

vfs_unlink():
  鈶?ext4_unlink() 鈫?浠庣洰褰曞垹闄ょ洰褰曢」 鈫?[i_nlink=0, i_count=1]
  鈶?d_delete() 鈫?鎽橀櫎 dentry 鈫?iput() 鈫?[i_nlink=0, i_count=0]
  鈶?鈫?evict() 閲婃斁 inode 鉁?
浣嗗鏋滄湁鍙︿竴涓繘绋嬪凡缁?open() 浜嗚繖涓枃浠讹細
  鈫?[i_nlink=0, i_count=2]  鈫?file 瀵硅薄涔熸寔鏈夊紩鐢?  鈫?d_delete() 鍙噴鏀句簡 dentry 鐨勫紩鐢?鈫?[i_nlink=0, i_count=1]
  鈫?inode 杩樺湪锛佽繘绋嬪彲浠ョ户缁鍐?  鈫?close() 鍚?i_count-- 鈫?[i_nlink=0, i_count=0] 鈫?閲婃斁 鉁?```

杩欏氨鏄?鏂囦欢宸插垹闄わ紝绌洪棿鏈噴鏀撅紝杩涚▼杩樺湪璇诲啓"鍦烘櫙鐨勫師鐞嗐€?
### RCU 璺緞鐨勯澶栦繚鎶?
```c
// 鍗充娇 RCU 鏃犻攣璺緞涔熼€氳繃 seqcount 妫€娴嬪苟鍙戜慨鏀癸細
seq = read_seqcount_begin(&dentry->d_seq);
inode = dentry->d_inode;
if (read_seqcount_retry(&dentry->d_seq, seq))
    goto fail;  // 琚敼浜?鈫?鏀惧純 鈫?璧板甫閿佽矾寰勯噸鏌?```

---

## ext2/ext3 鐨?inode 瀛樺偍鍦ㄥ摢閲岋紵

**鍜?ext4 瀹屽叏涓€鏍枫€?* 涓夌鏂囦欢绯荤粺鍏辩敤鍚屼竴濂楃鐩樺竷灞€鈥斺€斿潡缁勶紙Block Group锛夋ā鍨嬨€?
```
姣忎釜 Block Group锛?鈹屸攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹?鈹?Super  鈹?Group  鈹?Block  鈹?Inode        鈹?Data         鈹?鈹?Block  鈹?Desc   鈹?Bitmap 鈹?Bitmap       鈹?Blocks       鈹?鈹?(澶囦唤) 鈹?       鈹?       鈹?             鈹?             鈹?鈹斺攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹粹攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹粹攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹粹攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹粹攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹?                              鈻?             鈻?                       inode 琛ㄥ瓨杩欓噷  鏂囦欢鍐呭瀛樿繖閲?```

inode 琛ㄥ湪鍧楃粍涓殑浣嶇疆鐢?Group Descriptor 璁板綍銆俵ookup() 鍦ㄧ洰褰曟枃浠跺唴瀹逛腑鎵惧埌鏂囦欢鍚?鈫?鎷垮埌 inode 鍙?鈫?璁＄畻鎵€鍦ㄥ潡缁?鈫?瀹氫綅鍒拌鍧楃粍鐨?Inode Table 鈫?鎸夊亸绉婚噺璇诲彇 inode 鏉＄洰銆?
**鏍煎紡鍖栨椂 inode 鎬绘暟灏卞畾姝讳簡**锛歚inode_count = 鍒嗗尯澶у皬 / inode_ratio`锛堥粯璁?16384 瀛楄妭涓€涓?inode锛夈€俙tune2fs -l /dev/sda1` 鏌ョ湅鍏蜂綋鏁板€笺€?
**鍥哄畾缂栧彿**锛歩node #1 = 鍧忓潡鍒楄〃锛宨node #2 = 鏍圭洰褰曪紙姘镐笉鏀瑰彉锛夈€傛渶鏃╁彲鐢ㄧ殑鏄?#11銆?
---

## dcache 鐨勮璁℃剰鍥炬槸浠€涔堬紵

娌℃湁 dcache 鐨勪笘鐣屸€斺€旀瘡娆¤矾寰勮В鏋愰兘瀹屾暣璧扮鐩?I/O锛?
```c
// 鏃犳暟娆￠噸澶嶇殑 I/O
// 姣忎釜 cd銆乴s銆乧at 閮戒粠澶存潵涓€閬?lookup("/home/user/project/doc.txt") {
    root = read_disk_inode(2);           // I/O
    home = read_dir(root, "home");       // I/O
    home_inode = read_disk_inode(...);   // I/O
    user = read_dir(home, "user");       // I/O
    // ... 鏃犳灏界殑 I/O
}
```

dcache 鐨勪笁澶ц璁′娇鍛斤細

### 鈶?璺緞瑙ｆ瀽鍔犻€?绗竴娆¤闂蛋瀹屾暣 I/O 鈫?缁撴灉缂撳瓨鍦?dcache 鏍戜腑 鈫?绗簩娆?lookup_fast 鍏ㄥ懡涓?鈫?**闆舵纾佺洏 I/O**銆?
### 鈶?鍑忓皯閲嶅 inode 鍔犺浇锛堝紩鐢ㄨ鏁板叡浜級
鍚屼竴鏂囦欢琚墦寮€涓ゆ锛氫袱涓?dentry 鎸囧悜鍚屼竴涓?inode锛宨node->i_count = 2銆傚悇鑷?close 鍚?i_count 閫掑噺浣嗕笉涓?0銆俤cache 浠嶄繚鐣?dentry锛宨node 闀挎湡椹荤暀銆?
### 鈶?璐熺紦瀛?"鏂囦欢涓嶅瓨鍦?涔熺紦瀛樹笅鏉ワ紝閬垮厤鍙嶅璧?I/O 纭涓嶅瓨鍦ㄣ€傝繖瀵圭紪璇戠瓑鍦烘櫙灏ゅ叾閲嶈鈥斺€攇cc 鍦ㄥ涓?include 璺緞鎼滅储澶存枃浠讹紝姣忎釜涓嶅瓨鍦ㄩ兘闈犺礋缂撳瓨闆舵垚鏈繑鍥炪€?
### 浠ｄ环涓庣瓥鐣?| 鏈哄埗 | 涓轰粈涔?| 鎬庝箞鍋?|
|------|--------|--------|
| LRU 鍥炴敹 | 鍐呭瓨鏈夐檺 | 鎸夋渶杩戜娇鐢ㄦ椂闂存帓搴忥紝浼樺厛鍥炴敹璐?dentry |
| d_prune | 鏂囦欢琚垹闄?| 瀵瑰簲鐨?dentry 浠?dcache 鏍戞憳鎺?|
| shrink_dcache_parent() | 鐩綍琚垹闄?| 閫掑綊娓呯悊瀛愮洰褰曠殑鎵€鏈?dentry |
| dentry_hashtable | 鏌ユ壘鍔犻€?| 32768 涓《鐨勫搱甯岃〃锛孫(1) lookup |

---

## lookup_slow 鐨勫苟鍙戦槻鎶わ細涓や釜 CPU 鍚屾椂鍙戣捣鐩稿悓 I/O 鎬庝箞鍔烇紵

**鍐呮牳鏈変笁閬撻槻绾匡紝灞傚眰閫掕繘銆?*

### 绗竴閬撻槻绾匡細inode 淇″彿閲忥紙鏈€鏍稿績锛?
```c
// fs/namei.c 鈥?lookup_slow()
static struct dentry *lookup_slow(struct dentry *dentry, unsigned int flags)
{
    struct inode *inode = d_inode(dentry->d_parent);

    inode_lock_shared(inode);  // 鈫?鎷跨埗鐩綍鐨勮淇″彿閲?
    // 鎷垮埌閿佸悗锛屽啀鏌ヤ竴娆?dcache锛堥槻姝㈠彟涓€涓?CPU 宸茬粡鎻掑叆浜嗭級
    dentry = __d_lookup(dentry->d_parent, &dentry->d_name);
    if (dentry)
        goto out;  // 鍙︿竴涓?CPU 宸茬粡鎼炲畾浜?鈫?鐩存帴澶嶇敤

    // 鐪熺殑娌℃湁 鈫?鍋?I/O
    dentry = inode->i_op->lookup(inode, dentry, flags);

out:
    inode_unlock_shared(inode);
    return dentry;
}
```

鏁堟灉锛?
```
CPU 0                          CPU 1
鈹?                              鈹?鈹溾攢 lookup_slow("doc.txt")       鈹溾攢 lookup_slow("doc.txt")
鈹?  鈹溾攢 inode_lock_shared()      鈹?  鈹溾攢 inode_lock_shared()
鈹?  鈹?  鎷垮埌閿?鉁?              鈹?  鈹?  绛夐攣鈥︹€?鈴?鈹?  鈹溾攢 __d_lookup() 鈫?鏈懡涓?   鈹?  鈹?  锛堣闃诲锛?鈹?  鈹溾攢 ext4_lookup() 鈫?I/O      鈹?  鈹?鈹?  鈹溾攢 d_add() 鈫?鍒涘缓 dentry    鈹?  鈹?鈹?  鈹溾攢 inode_unlock_shared()    鈹?  鈹? 鈫?閿侀噴鏀?鈹?                              鈹溾攢鈹€鈫?鎷垮埌閿?鉁?鈹?                              鈹溾攢 __d_lookup() 鈫?鍛戒腑锛侌煄?鈹?                              鈹?  鐩存帴澶嶇敤 CPU 0 鐨?dentry锛岄浂 I/O锛?鈹?                              鈹斺攢 inode_unlock_shared()
```

娉ㄦ剰鐢ㄧ殑鏄?`inode_lock_shared()`锛?*璇讳俊鍙烽噺**锛夆€斺€斿悓涓€鐩綍涓嬭В鏋?*涓嶅悓**鏂囦欢鍚嶆椂锛屽涓?CPU 鍙苟鍙戣繘鍏?lookup_slow锛屼笉浜掓枼銆傚彧鏈夊垱寤?鍒犻櫎鏂囦欢锛堝啓鎿嶄綔锛夋墠鎷垮啓閿併€?
### 绗簩閬撻槻绾匡細鍝堝笇妗惰嚜鏃嬮攣

```c
// fs/dcache.c 鈥?d_rehash()
static void __d_rehash(struct dentry *entry, struct hlist_bl_head *b)
{
    hlist_bl_lock(b);                              // 姣忎釜妗舵湁鑷棆閿?    hlist_bl_add_head_rcu(&entry->d_hash, b);
    hlist_bl_unlock(b);
}
```

闃叉涓や釜 dentry 骞跺彂鎻掑叆鍚屼竴涓搱甯屾《銆?
### 绗笁閬撻槻绾匡細buffer head 閿?
鍦?ext4 璇诲彇鐩綍鏂囦欢鏁版嵁鍧楁椂锛宍ext4_bread()` 鈫?`__block_read_full_folio()` 鈫?`submit_bh()` 璺緞涓紝buffer head 鐨?`bh->b_lock` 涓茶鍖栧鍚屼竴纾佺洏鍧楃殑 I/O銆?
### 鎬荤粨

| 闃茬嚎 | 鏈哄埗 | 绮掑害 | 鏁堟灉 |
|------|------|------|------|
| 鈶?inode 淇″彿閲?| `inode_lock_shared()` | 鐖剁洰褰曠矑搴?| 鉁?闃叉鍚屼竴鐩綍涓嬬殑鍐椾綑 I/O |
| 鈶?鍝堝笇妗惰嚜鏃嬮攣 | `hlist_bl_lock(b)` | d_hash 妗剁矑搴?| 鉁?闃叉閲嶅 dentry 鎻掑叆 |
| 鈶?buffer head 閿?| bh->b_lock / folio lock | 纾佺洏鍧楃矑搴?| 鉁?闃叉鍚屽潡 I/O 绔炰簤 |

璁捐鍝插锛?*鍚屼竴鐩綍涓茶鍖栵紙闃叉鍐椾綑 I/O 鍜?race锛夛紝涓嶅悓鐩綍骞惰鍖栵紙鍏呭垎鍒╃敤澶氭牳锛夈€?*

---

## bind mount 鍦烘櫙锛氫袱涓?mount 鐐癸紝鍚屼竴涓洰褰曪紝涓や釜 CPU 浼氬仛閲嶅 I/O 鍚楋紵

**涓嶄細銆傚洜涓洪攣鐨勬槸 inode锛屼笉鏄?dentry銆?* bind mount 鐨勪袱涓?dentry 涓嶅悓锛屼絾瀹冧滑鎸囧悜鐨?*鐖剁洰褰?inode 鏄悓涓€涓?*銆?
```
mount /dev/sdb1 /mnt/point1
mount --bind /mnt/point1/subdir /mnt/point2

璺緞A锛?mnt/point1/subdir/doc.txt
  鈫?瑙ｆ瀽 "doc.txt" 鏃讹紝鐖剁洰褰?inode = #300

璺緞B锛?mnt/point2/doc.txt
  鈫?瑙ｆ瀽 "doc.txt" 鏃讹紝鐖剁洰褰?inode = #300锛堝悓涓€涓紒锛?
CPU A锛歩node_lock_shared(inode #300)  鈫?鎷垮埌閿?鉁?CPU B锛歩node_lock_shared(inode #300)  鈫?绛夐攣鈥︹€?鈴?                                       鈫?绛?A 閲婃斁閿佸悗锛屼粠 dcache 鍛戒腑 鉁?```

鎵€浠ヤ袱涓?CPU 浠嶇劧琚?inode 閿佷覆琛屽寲浜嗏€斺€斾笉浼氭湁涓や釜閲嶅 I/O銆?
**浣犺鐨?I/O 鍚堝苟锛圛/O scheduler merging锛夊湪杩欎釜鍦烘櫙涓嶄細涓婂満**锛屽洜涓虹浜?CPU 鍦?VFS 灞傚氨琚嫤浣忎簡锛屾牴鏈笉浼氬彂 I/O 璇锋眰鍒板潡灞傘€?
I/O 鍚堝苟鐪熸鏈夋晥鐨勫湴鏂癸細**涓や釜杩涚▼ read 鍚屼竴涓枃浠剁殑涓嶅悓閮ㄥ垎**鈥斺€旇繖鏃朵笉閿?inode锛堟枃浠舵暟鎹涓嶉攣鐩綍 inode锛夛紝涓や釜 I/O 鍙互骞跺彂銆傚鏋滅鐩樺潡鏄繛缁殑锛孖/O scheduler 鍙互鍚堝苟涓轰竴娆℃洿澶х殑 I/O銆?
---

## lookup_slow 閿佺殑鏄摢涓?inode锛熻矾寰勮秺闀块攣鐨?inode 瓒婂锛?
**閿佺殑鏄?褰撳墠姝ｅ湪鏌ユ壘鐨勫垎閲忔墍鍦ㄧ殑鐖剁洰褰?inode"锛屼笉鏄?mount 缁撴瀯鐨?inode銆傛瘡灞傜敤瀹屽嵆閲婃斁锛屼笉浼氱Н绱€?*

```c
static struct dentry *lookup_slow(struct dentry *dentry, unsigned int flags)
{
    struct inode *inode = d_inode(dentry->d_parent);
    inode_lock_shared(inode);          // 鈫?閿佺埗鐩綍
    dentry = __d_lookup(...);
    if (!dentry)
        dentry = inode->i_op->lookup(...);  // I/O
    inode_unlock_shared(inode);        // 鈫?閲婃斁閿侊紒
    return dentry;                     // 鈫?閿佸凡缁忛噴鏀句簡锛?}
```

涓句緥锛氳В鏋?`/home/user/project/doc.txt`锛?
```
绗?灞傦細瑙ｆ瀽 "home"  鈫?inode_lock_shared(inode#2) 鈫?I/O 鈫?閲婃斁 鉁?绗?灞傦細瑙ｆ瀽 "user"  鈫?inode_lock_shared(inode#12) 鈫?I/O 鈫?閲婃斁 鉁?绗?灞傦細瑙ｆ瀽 "project" 鈫?inode_lock_shared(inode#45) 鈫?I/O 鈫?閲婃斁 鉁?绗?灞傦細瑙ｆ瀽 "doc.txt" 鈫?inode_lock_shared(inode#78) 鈫?I/O 鈫?閲婃斁 鉁?```

閿佺殑鎸佹湁鏃堕棿闈炲父鐭€斺€斿彧瑕嗙洊涓€娆?I/O锛岃矾寰勫垎閲忚В鏋愬畬椹笂閲婃斁銆?*涓嶆槸涓€娆℃€ч攣鍏ㄩ儴锛岃€屾槸涓€灞傚眰閫掕繘銆佺敤瀹屽嵆鏀俱€?*

---

## 璺緞瓒婇暱閿佸啿绐佽秺澶氾紵浣嗘牴鐩綍鎵嶆槸鏈€鐑殑鍚э紵

浣犵殑涓や釜鐩磋閮芥槸瀵圭殑锛屼絾鍏抽敭鍖哄埆鍦ㄤ簬锛?*lookup_slow() 鍙湪 dcache 鏈懡涓椂璋冪敤銆傛牴鐩綍鐨?dentry 姘镐笉鍑虹紦瀛橈紙d_count 琚涓案涔呭紩鐢ㄦ寔鏈夛級锛屾墍浠ユ牴鐩綍 lookup 浠庝笉閿併€?*

```
绗竴娆￠亶鍘?/a/b/c/d/file.txt锛?
  "/"     鈫?lookup_fast 鍛戒腑 鉁?     鉂?涓嶉攣锛堟牴 dentry 姘歌繙鍦?dcache锛?  "a"     鈫?lookup_fast 鏈懡涓?      馃敀 inode_lock("/")    寰
  "b"     鈫?lookup_fast 鏈懡涓?      馃敀 inode_lock("a")    寰
  "c"     鈫?lookup_fast 鏈懡涓?      馃敀 inode_lock("b")    寰
  "d"     鈫?lookup_fast 鏈懡涓?      馃敀 inode_lock("c")    寰
  "file"  鈫?lookup_fast 鏈懡涓?      馃敀 inode_lock("d")    寰

绗簩娆￠亶鍘嗭紙鍏ㄩ儴 cached锛夛細
  "/" 鈫?"a" 鈫?"b" 鈫?"c" 鈫?"d" 鈫?"file"
  鍏?lookup_fast 鍛戒腑 鉁?  閿佹鏁?= 0
```

**鍏抽敭缁撹锛歩node 閿佺殑鍐茬獊鐐逛笉鍦?璺緞闀?锛岃€屽湪"鐩綍鐑?鈥斺€斿嵆澶ч噺杩涚▼棰戠箒鍦ㄨ鐩綍涓嬪垱寤?鍒犻櫎鏂囦欢銆?*

| 鍦烘櫙 | 鐡堕 |
|------|------|
| 娣卞害璺緞绗竴娆¤闂?| 鐩綍娣卞害 脳 I/O 娆℃暟锛堝喎鍚姩锛?|
| 娣卞害璺緞绗簩娆¤闂?| 闆堕攣锛坉cache 鍏ㄨ鐩栵級 |
| /tmp 涓嬮绻?create/unlink | 鐩綍鐑害锛?tmp 鐨?inode 閿佺珵浜夛級 |
| /var/log/ 涓嬫棩蹇楄疆杞?| 鐩綍鐑害 + 鏂囦欢璇诲啓甯﹀ |

---

## 鎬ц兘鍒嗘瀽妗嗘灦锛氭繁搴?+ 鐑害 + 鏁版嵁閲?
浣犵殑鎬荤粨灏辨槸鏈€缁堢粨璁猴細

**鐩綍娣卞害鍐冲畾浜嗗喎鍚姩鐨?I/O 娆℃暟锛岀洰褰曠儹搴﹀喅瀹氫簡澶氳繘绋嬪苟鍙戞椂鐨勯攣绔炰簤锛屾暟鎹噺锛堣鍐欏甫瀹斤級鍐冲畾浜嗛〉闈㈢紦瀛樺拰纾佺洏鍚炲悙銆?*

```
鏂囦欢绯荤粺鎬ц兘 = 鐩綍娣卞害锛堝喎鍚姩 I/O锛?+ 鐩綍鐑害锛堥攣绔炰簤锛?+ 鏁版嵁閲忥紙璇诲啓甯﹀锛?                  鈫?                   鈫?                      鈫?             璺緞瑙ｆ瀽闃舵          鍏冩暟鎹搷浣滈樁娈?          鏁版嵁鎿嶄綔闃舵
             open/stat 鏃?         create/unlink 鏃?        read/write 鏃?```

---

---

## 鏂囦欢鍋忕Щ >> PAGE_SHIFT 鏄粈涔堜綔鐢紵

杩欐槸 **"瀛楄妭鍋忕Щ 鈫?椤电储寮?** 鐨勮浆鎹€?
`PAGE_SHIFT` 涓嶆槸姣忛〉澶у皬鏈韩锛岃€屾槸**椤靛ぇ灏忎互 2 涓哄簳鐨勫鏁?*锛?
```
PAGE_SIZE = 4096 瀛楄妭锛?KB锛?PAGE_SHIFT = 12锛堝洜涓?2^12 = 4096锛?```

鎵€浠?`offset >> PAGE_SHIFT` 灏辨槸鎶婂瓧鑺傚亸绉婚噺闄や互 4096锛屽緱鍒?杩欐槸绗嚑椤?锛?
```c
pgoff_t index = iocb->ki_pos >> PAGE_SHIFT;
//              鏂囦欢鍋忕Щ閲忥紙瀛楄妭锛?>> 12
//              4096      >> 12 = 1  鈫?绗?1 椤碉紙浠?0 寮€濮嬭鏁帮級
//              8192      >> 12 = 2  鈫?绗?2 椤?//              0         >> 12 = 0  鈫?绗?0 椤?//              5000      >> 12 = 1  鈫?涔熸槸绗?1 椤碉紙鍚戜笅瀵归綈鍒伴〉杈圭晫锛?```

xarray 涓瓨鍌ㄧ殑 key 灏辨槸杩欎釜 `pgoff_t index`锛屾墍浠ョ粰瀹氭枃浠跺亸绉诲氨鑳?O(1) 鎵惧埌 page cache 涓殑椤点€?
涓嶅悓鏋舵瀯鐨?PAGE_SHIFT锛?
| 鏋舵瀯 | PAGE_SIZE | PAGE_SHIFT |
|------|-----------|-----------|
| x86-64 | 4096 (4KB) | **12** |
| ARM64 (4KB 椤? | 4096 | **12** |
| ARM64 (16KB 椤? | 16384 | **14** |
| PPC (64KB 椤? | 65536 | **16** |

**涓轰粈涔堢敤绉讳綅鑰屼笉鏄箻闄わ紵** 鍥犱负浣嶈繍绠楁槸涓€鏉?CPU 鎸囦护锛岄櫎娉曟槸 ~30 鏉℃寚浠ゃ€傚唴鏍镐唬鐮佷腑鎵€鏈?瀛楄妭 offset 鈫?椤?index"鐨勮浆鎹㈤兘鐢ㄧЩ浣嶃€?
---

## flusher 绾跨▼鎬庝箞鎵惧埌鑴忛〉锛熼渶瑕佹壂鎻忔墍鏈?page cache 鍚楋紵

**涓嶉渶瑕佹壂鎻忓叏閮ㄣ€?* flusher 绾跨▼鏈夋洿楂樻晥鐨勬暟鎹粨鏋勨€斺€?*姣忎釜 inode 鐨勮剰椤甸€氳繃绾㈤粦鏍戠粍缁囧湪 address_space 鐨?xarray 涓紝鍚屾椂鏁翠釜绯荤粺鐨勮剰 inode 閫氳繃閾捐〃涓茶仈銆?*

### 鏁版嵁缁撴瀯閾?
```
姣忎釜鏂囦欢绯荤粺瓒呯骇鍧?  鈹斺攢鈹€ s_dirty 閾捐〃锛氭墍鏈?鍖呭惈鑴忛〉"鐨?inode
        鈹?        鈹溾攢鈹€ inode #42 (i_dirty_list)
        鈹?    鈹斺攢鈹€ xarray 涓殑鑴忛〉浣嶅浘锛堝摢涓€椤垫槸鑴忕殑锛?        鈹?        鈹溾攢鈹€ inode #78 (i_dirty_list)  
        鈹?    鈹斺攢鈹€ xarray 涓殑鑴忛〉浣嶅浘
        鈹?        鈹斺攢鈹€ inode #106 (i_dirty_list)
              鈹斺攢鈹€ xarray 涓殑鑴忛〉浣嶅浘
```

flusher 绾跨▼鐨勬牳蹇冨惊鐜細

```c
// fs/fs-writeback.c 鈥?wb_writeback()
long wb_writeback(struct bdi_writeback *wb, struct wb_writeback_work *work)
{
    for (;;) {
        // 鈽?浠庤秴绾у潡鐨?s_dirty 閾捐〃涓彇鍑轰竴涓剰 inode
        inode = list_first_entry(&sb->s_dirty, struct inode, i_dirty_list);
        
        // 鍙壂鎻忚繖涓?inode 鐨勮剰椤?        writeback_single_inode(inode, wb, work);
        //   鈫?閬嶅巻 xarray 涓爣璁颁负 dirty 鐨勯〉
        //   鈫?a_ops->writepage() 閫愰〉鍥炲啓
        
        // 妫€鏌ユ槸鍚﹀埌杈鹃槇鍊?        if (pages_written >= work->nr_pages)
            break;
    }
}
```

### 鍏抽敭缁撹

| flusher 涓嶉渶瑕佸仛鐨勪簨 | flusher 瀹為檯鍋氱殑浜?|
|-------------------|------------------|
| 鉂?鎵弿鎵€鏈?page cache 椤?| 鉁?鍙亶鍘?`s_dirty` 閾捐〃 |
| 鉂?妫€鏌ユ瘡涓〉鏄惁涓鸿剰 | 鉁?`s_dirty` 閾捐〃涓彧鏀炬湁鑴忛〉鐨?inode |
| 鉂?閬嶅巻 xarray 鍏ㄩ儴鏉＄洰 | 鉁?鍙洖鍐欐爣璁颁负 dirty 鐨勯〉 |

**姣忎釜鏍囪杩囩▼**鈥斺€斿啓鑴忛〉鏃讹紝`mark_buffer_dirty()` 浼氬仛涓や欢浜嬶細

```c
// fs/buffer.c 鈥?mark_buffer_dirty()
void mark_buffer_dirty(struct buffer_head *bh)
{
    struct folio *folio = bh->b_folio;
    struct address_space *mapping = folio->mapping;

    if (!folio_test_set_dirty(folio)) {
        // 鈽?杩欎釜 folio 鍒氳棣栨鏍囪涓鸿剰
        //    鎶婂畠鐨?inode 鍔犲叆瓒呯骇鍧楃殑 s_dirty 閾捐〃锛堝鏋滆繕娌″姞鍏ワ級
        if (mapping->host->i_state & I_DIRTY) {
            // 宸茬粡鍦ㄩ摼琛ㄤ腑浜?        } else {
            spin_lock(&sb->s_inode_list_lock);
            list_add_tail(&mapping->host->i_dirty_list, &sb->s_dirty);
            spin_unlock(&sb->s_inode_list_lock);
        }
    }
}
```

**鑴?inode 鏄?鎸夐渶鍔犲叆閾捐〃"鐨?*锛屼笉鏄?flusher 鍘诲彂鐜板畠銆俧lusher 鍙渶瑕佷粠閾捐〃澶村彇鑺傜偣澶勭悊灏辫銆?
鎶婅繖涓笌浣犵殑涓婁竴璇鹃棶棰樼粨鍚堚€斺€?*鎵€鏈夐珮鏁堝唴鏍告満鍒堕兘閬靛惊鍚屾牱鐨勬ā寮忥細涓嶆槸鍦ㄩ渶瑕佹椂鍘绘壂鎻忓叏閮ㄦ潵鎵撅紝鑰屾槸鍦ㄦ搷浣滃彂鐢熸椂灏卞皢鑷繁娉ㄥ唽鍒版煇涓摼琛?鍝堝笇琛?鏍戜腑锛岃娑堣垂鑰咃紙flusher銆佸洖鏀跺櫒锛夊彧闇€閬嶅巻宸茬煡鐨?鍊欓€夊垪琛?銆?*

---

## folio 鏄粈涔堢殑缂╁啓锛?
**涓嶆槸缂╁啓銆?* Folio 鏄嫳鏂囧崟璇嶆湰韬紙鍘熸剰"瀵规姌鐨勭焊/椤电爜"锛夛紝鍦ㄥ唴鏍镐腑浠ｈ〃"涓€涓垨澶氫釜杩炵画鐨勭墿鐞嗛〉缁勬垚鐨勫鍣?銆俧olio 缁熶竴浜?API鈥斺€斿嚱鏁扮鍚嶅啓 `struct folio *` 鏃跺氨鏄庣‘琛ㄧず"鍙互鎿嶄綔 1锝濶 涓繛缁〉"銆?
鏂拌€?API 瀵瑰簲锛?
| 鑰佷唬鐮?| 鏂颁唬鐮?| 鍚箟 |
|--------|--------|------|
| `page->mapping` | `folio->mapping` | 鎵€灞?address_space |
| `page->index` | `folio->index` | 鏂囦欢鍋忕Щ >> PAGE_SHIFT |
| `lock_page(page)` | `folio_lock(folio)` | 閿佷綇璇ラ〉 |
| `filemap_get_page()` | `filemap_get_folio()` | 浠?page cache 鑾峰彇 |

---

## read() 缂洪〉鏃讹細鍒嗛厤椤?鈫?鎻掑叆 xarray 鈫?I/O 鐨勯『搴忓強澶辫触澶勭悊

**鍏堝垎閰嶉〉 鈫?鎻掑叆 xarray 鈫?鍐嶅彂 I/O銆傚垎閰嶅け璐ュ氨涓嶅彂 I/O锛岀洿鎺ヨ繑鍥?-ENOMEM銆?*

```c
struct folio *filemap_create_folio(struct address_space *mapping, pgoff_t index)
{
    folio = filemap_alloc_folio(gfp);       // 鈶?鍒嗛厤鐗╃悊椤垫
    if (!folio) return ERR_PTR(-ENOMEM);    //    鍐呭瓨涓嶈冻鐩存帴杩斿洖

    error = filemap_add_folio(mapping, folio, index, gfp);  // 鈶?鎻掑叆 xarray
    if (error) goto error;                  //    宸茶鍏朵粬 CPU 鍏堟彃鍏?
    error = mapping->a_ops->read_folio(file, folio);        // 鈶?鍙?I/O
    if (error) {
        filemap_remove_folio(folio);        // I/O 澶辫触 鈫?浠?xarray 鍒犻櫎
        folio_put(folio);                   // 閲婃斁椤垫
        return ERR_PTR(error);              // 杩斿洖 -EIO
    }
    return folio;
}
```

纾佺洏 I/O 澶辫触鏃讹細page cache 椤佃鍒犻櫎锛岄〉妗嗛噴鏀撅紝read() 杩斿洖 `-EIO`銆?
**鍏充簬 filemap_add_folio() 鐨勫苟鍙戦槻鎶?*锛氬畠涓?lookup_slow 鐨勮璁″畬鍏ㄤ竴鑷粹€斺€擿xa_lock` 鍚?`xa_load()` 鍐嶆煡涓€娆★紝濡傛灉鍙︿竴涓?CPU 宸叉彃鍏ワ紝灏遍噴鏀捐嚜宸卞垰鍒嗛厤鐨勯〉锛屽鐢ㄥ凡鏈夌殑銆?
---

## 棰勮鐨勫垽鏂満鍒垛€斺€斾粠绗竴娆?read 灏卞紑濮嬶紵

**浼氥€?* 鍐呮牳浠庣涓€娆?read锛坧age cache 缂洪〉锛夊氨寮€濮嬪皾璇曢璇汇€?
```c
// 绗竴娆＄己椤?鈫?ra->size == 0 鈫?鐢ㄥ垵濮嬮璇诲ぇ灏忥紙榛樿 4 椤?= 16KB锛?initial_readahead = get_init_ra_size(index, ra->ra_pages);
```

**鏂囦欢鍙湁 4096 瀛楄妭鍛紵浼氫笉浼氬璇昏秴鍑烘枃浠讹紵涓嶄細銆?* 棰勮鍙楁枃浠跺ぇ灏忛檺鍒讹細

```c
max_pages = (i_size_read(mapping->host) - index * PAGE_SIZE) / PAGE_SIZE;
ra->size = min(initial, max_pages);  // 涓嶄細瓒呭嚭鏂囦欢鏈熬
```

濡傛灉鏂囦欢鍙湁 4096 瀛楄妭锛岄璇诲ぇ灏?= `min(4, 1) = 1`锛屼笉浼氳鍒版枃浠跺闈㈠幓銆?
---

## Page Cache 涓庣墿鐞嗗唴瀛樺洖鏀剁殑鍏崇郴

Page Cache 鍗犵敤鐨勭墿鐞嗛〉妗嗘槸鍐呭瓨鍥炴敹鐨勯瑕佺洰鏍囷細

```
鍐呭瓨鍘嬪姏 鈫?kswapd/direct reclaim 鈫?shrink_lruvec() 鈫?鎵弿 LRU 閾捐〃
  鈫?閬囧埌 file-backed 椤碉細
    鈹溾攢 骞插噣椤?鈫?鐩存帴鍥炴敹锛堥〉妗嗛噴鏀撅紝鍐呭宸插湪纾佺洏锛?    鈹斺攢 鑴忛〉 鈫?蹇呴』鍏堝啓鍥烇紙writeback锛夛紝鎵嶈兘鍥炴敹
```

Page Cache 鍙洖鏀舵槸 Linux 鍐呭瓨绠＄悊鐨勫熀鏈亣璁锯€斺€旂┖闂插唴瀛樹笉澶熸椂锛屽唴鏍镐細鍘嬬缉 page cache 鏉ラ噴鏀惧唴瀛樸€?
### 椤甸潰鍥炴敹涓?writeback 鐨勫叧绯?
褰撳唴瀛樺帇鍔涘ぇ鍒颁竴瀹氱▼搴︼紝鍥炴敹閫昏緫浼氬己鍒跺皢鑴忛〉鍐欏洖纾佺洏锛岀劧鍚庨噴鏀鹃〉妗嗐€傝繖灏辨槸涓轰粈涔?`dirty_background_ratio` 鍜?`dirty_ratio` 瑕佷笌鍐呭瓨鍥炴敹鏈哄埗閰嶅悎鐪嬧€斺€攄irty 姣斾緥澶珮浼氬鑷村ぇ閲忓悓姝ュ洖鍐欙紝寮曞彂绯荤粺鎬ц兘鎶栧姩銆?
---

## 鑴忛〉鍥炲啓鐨勪袱涓淮搴?+ flusher 鍐呮牳绾跨▼

**纭疄鏈変笓闂ㄧ殑鍐呮牳绾跨▼姹犫€斺€攆lusher 绾跨▼锛堜互鍓嶅彨 pdflush锛夈€?*

| 瑙﹀彂鏉′欢 | 瀵瑰簲鍙傛暟 | 榛樿鍊?| 鏁堟灉 |
|---------|---------|--------|------|
| 鑴忛〉姣斾緥瓒呰繃闃堝€?| `dirty_background_ratio` | 10% | 鍚庡彴 flusher 绾跨▼寮€濮嬪啓鍥?|
| 鑴忛〉姣斾緥杈惧埌纭笂闄?| `dirty_ratio` | 20% | 鍚屾闃诲鏂扮殑 write() |
| 鑴忛〉瀛樺湪鏃堕棿杩囨湡 | `dirty_expire_centisecs` | 3000 (30绉? | flusher 瀹氭湡鎵弿杩囨湡鑴忛〉 |
| 鍛ㄦ湡鎬ф鏌?| `dirty_writeback_centisecs` | 5000 (5绉? | flusher 姣忛殧 5 绉掑敜閱掓鏌?|

**鍚屾闃诲鏈哄埗**锛氭瘡娆?write() 璺緞閮戒細璧?`balance_dirty_pages()`锛屽垽鏂剰椤垫瘮渚嬨€傝秴杩囩‖涓婇檺鏃讹紝搴旂敤绋嬪簭琚揩绛夊緟銆?
---

## 棰勮闅忔満璁块棶鍚庝細涓嶄細鎭㈠锛熸瘡娆?read 閮藉仛鍒ゆ柇鍚楋紵

**浼氭仮澶嶃€?* 褰撹闂ā寮忎粠闅忔満鎭㈠涓洪『搴忔椂锛岄璇昏嚜鍔ㄦ仮澶嶃€備笉闇€瑕佹樉寮忚Е鍙戔€斺€斿彧鏄獥鍙ｅぇ灏忓彉浜嗐€傚鏋滃悗缁姹傚彉鎴愰『搴忕殑锛岀獥鍙ｄ粠鍒濆鍊硷紙4 椤碉級閲嶆柊寮€濮嬮€掑鑶ㄨ儉銆?
**姣忔 read 閮藉仛鍒ゆ柇**鈥斺€擿page_cache_sync_readahead()` 鍦ㄦ瘡娆?`filemap_read()` 涓兘浼氳璋冪敤锛屼絾寮€閿€鏋佷綆锛堟瘮杈?`index == ra->start + ra->size` 鍑犱釜鏁存暟锛夛紝鏃犻澶?I/O銆?
---

## 涓や釜杩涚▼ read 鍚屼竴涓枃浠舵湭鍛戒腑鏃剁殑绔炰簤

涓?lookup_slow 鐨勮璁″畬鍏ㄤ竴鑷达細

```
杩涚▼ A                                  杩涚▼ B
鈹?                                       鈹?鈹溾攢 filemap_get_folio() 鈫?NULL            鈹溾攢 filemap_get_folio() 鈫?NULL
鈹?                                       鈹?鈹溾攢 filemap_create_folio()                鈹溾攢 filemap_create_folio()
鈹?  鈹溾攢 alloc_page() 鈫?椤?A               鈹?  鈹溾攢 alloc_page() 鈫?椤?B
鈹?  鈹溾攢 xa_lock()                         鈹?  鈹溾攢 xa_lock()锛堢瓑 A 鈴筹級
鈹?  鈹溾攢 xa_load() 鈫?NULL                  鈹?  鈹?鈹?  鈹溾攢 xa_store(page A)                  鈹?  鈹?鈹?  鈹溾攢 xa_unlock()                       鈹?  鈹? 鈫?A 瑙ｉ攣
鈹?  鈹?                                   鈹溾攢鈹€鈫?鎷垮埌閿?鈹?  鈹溾攢 read_folio 鈫?I/O                  鈹?  鈹溾攢 xa_load() 鈫?page A锛堝凡鏈夛紒锛?鈹?  鈹?                                   鈹?  鈹溾攢 xa_unlock()
鈹?  鈹?                                   鈹?  鈹溾攢 folio_put(page B) 鈫?閲婃斁 B
鈹?  鈹?                                   鈹?  鈹斺攢 鐢?page A锛堢瓑 A 鐨?I/O 瀹屾垚锛?鈹?  鈹溾攢 I/O 瀹屾垚                          鈹?        鈹?鈹?  鈹斺攢 copy_page_to_iter(page A)         鈹?        鈫?琚敜閱?鈹?                                       鈹溾攢 copy_page_to_iter(page A)
鈹?                                       鈹斺攢 杩斿洖
```

绗簩涓?CPU 涓嶄細鍋?I/O鈥斺€斿畠绛夊緟绗竴涓?CPU 鐨?I/O 瀹屾垚鍚庣洿鎺ュ鐢ㄦ暟鎹€?
---

## address_space 鐨勪簲澶ц亴璐?
| 鑱岃矗 | 瀛楁 | 浣滅敤 |
|------|------|------|
| 鈶?page cache 绱㈠紩 | `i_pages` (xarray) | 瀛樺偍鏂囦欢鐨勬墍鏈夌紦瀛橀〉锛岀粰瀹氬亸绉?O(1) 鏌ユ壘 |
| 鈶?纾佺洏 I/O 鎺ュ彛 | `a_ops` (鎿嶄綔鍑芥暟琛? | `read_folio`銆乣writepage`銆乣dirty_folio`鈥斺€旀瘡涓枃浠剁郴缁熷疄鐜颁笉鍚?|
| 鈶?鍙嶅悜鏄犲皠锛坮map锛?| `i_mmap` (绾㈤粦鏍? | 瀛樺偍"鍝簺 VMA 鏄犲皠浜嗘枃浠剁殑鍝簺椤?锛屾崲鍑烘椂涓€閿竻闄ゆ墍鏈夐〉琛ㄩ」 |
| 鈶?鏂囦欢/鍖垮悕椤靛尯鍒?| `mapping` 鎸囬拡鐨?bit 0 | 0 = 鏂囦欢椤碉紝1 = 鍖垮悕椤碉紝涓嶆氮璐归澶栧瓧娈?|
| 鈶?I/O 绛夊緟闃熷垪 | 閫氳繃椤电殑 PG_locked 鏈哄埗 | 澶氫釜杩涚▼绛夊緟鍚屼竴椤?I/O 瀹屾垚鏃跺敜閱?|

**涓€涓患鍚堜緥瀛?*鈥斺€攎map 1GB 鏂囦欢锛屽唴瀛樺彧鏈?512MB锛?
```
鈶?mmap() 鈫?寤虹珛 VMA锛岃褰?inode 鈫?address_space
鈶?閬嶅巻鏃剁己椤?鈫?do_fault() 鈫?filemap_fault()
   鈫?i_pages 鏌ユ壘 鈫?鏈懡涓?鈫?a_ops->read_folio() 鈫?I/O 鈫?鎻掑叆 xarray
鈶?鍐呭瓨涓嶈冻 鈫?kswapd 寮€濮嬪洖鏀?   鈫?閫氳繃 address_space 鐨?i_mmap 鎵惧埌鎵€鏈夋槧灏勪簡璇ラ〉鐨?VMA
   鈫?娓呴櫎椤佃〃椤?   鈫?濡傛灉鑴?鈫?a_ops->writepage() 鍐欏洖
   鈫?閲婃斁椤垫
鈶?鐢ㄦ埛鍐嶆璁块棶 鈫?缂洪〉 鈫?filemap_fault() 鈫?閲嶆柊浠庣鐩樺姞杞?```

---

## 涓轰粈涔?folio->mapping 鐨?bit 0 鍙互鐢ㄦ潵鍋氭爣蹇椾綅锛?
鍥犱负 **`struct address_space` 鍜?`struct anon_vma` 鐨勫湴鍧€澶╃劧瀵归綈鍒?8 瀛楄妭**锛堢敱 slab 鍒嗛厤鍣ㄤ繚璇侊級锛屾墍浠ュ畠浠湴鍧€鐨?bit 0 姘歌繙涓?0銆傚唴鏍稿埄鐢ㄨ繖涓ぉ鐒剁┖闂茬殑浣嶅仛鏍囧織锛?
```c
#define PAGE_MAPPING_ANON      1  // bit 0 = 1 鈫?鍖垮悕椤?#define PAGE_MAPPING_KSM       2  // bit 1 = 1 鈫?KSM 鍚堝苟椤?#define PAGE_MAPPING_FLAGS     (PAGE_MAPPING_ANON | PAGE_MAPPING_KSM)

static inline struct anon_vma *folio_anon_vma(struct folio *folio)
{
    unsigned long mapping = (unsigned long)folio->mapping;
    if ((mapping & PAGE_MAPPING_ANON) == 0)
        return NULL;  // 鏂囦欢椤?    return (struct anon_vma *)(mapping & ~PAGE_MAPPING_FLAGS);
}
```

| bit 1 | bit 0 | 鍚箟 |
|-------|-------|------|
| 0 | 0 | 鏂囦欢椤?|
| 0 | 1 | 鍖垮悕椤?|
| 1 | 0 | KSM 鍚堝苟椤?|

**涓嶆氮璐逛竴涓濈┖闂?*鈥斺€斾竴涓?8 瀛楄妭鎸囬拡鍚屾椂鎵胯浇浜嗘湁鏁堝湴鍧€锛?8 浣嶏級鍜岄〉闈㈢被鍨嬫爣蹇楋紙浣?2 浣嶏級銆?
---

## mmap 璁块棶 vs read 璁块棶鈥斺€旇矾寰勫畬鍏ㄤ笉鍚?
| 缁村害 | read() | mmap 璁块棶 |
|------|--------|-----------|
| **鍏ュ彛** | 绯荤粺璋冪敤锛堣蒋浠堕櫡鍏ワ級 | 纭欢缂洪〉寮傚父锛圕PU 鑷姩瑙﹀彂锛?|
| **鏁版嵁澶嶅埗** | 闇€瑕?`copy_page_to_iter()` | **涓嶉渶瑕佸鍒?*鈥斺€旈〉琛ㄦ槧灏?page cache 鐨勭墿鐞嗛〉 |
| **绯荤粺璋冪敤寮€閿€** | 鏈?| **鏃?*锛堢己椤靛紓甯稿鐞嗗畬鐩存帴缁х画锛?|
| **鏂囦欢鍋忕Щ绠＄悊** | 鍐呮牳绠＄悊 `file->f_pos` | 鐢ㄦ埛绠＄悊锛堟寚閽堢Щ鍔級 |
| **page cache 浜ゆ眹** | file->f_mapping 鈫?address_space | VMA->vm_file->f_mapping 鈫?鍚屼竴涓?address_space |

**read() 澶氫簡涓€娆″唴瀛樺鍒讹紙page cache 鈫?鐢ㄦ埛缂撳啿鍖猴級锛宮map 閫氳繃椤佃〃鏄犲皠璺宠繃杩欐澶嶅埗銆傝繖灏辨槸"闆舵嫹璐?鐨勫惈涔夈€?* 浣?mmap 闇€瑕佸厛璋冪敤 mmap() 寤虹珛鏄犲皠鑼冨洿锛岃€?read() 涓嶉渶瑕佽繖涓墠缃楠ゃ€?
**涓よ€呴兘涓嶉渶瑕佸湪璇诲啓鏃堕噸鏂拌蛋 dcache/inode**鈥斺€攐pen() 鍜?mmap() 璋冪敤鏃跺凡瀹屾垚浜嗚矾寰勮В鏋愶紝鍚庣画閫氳繃 file 瀵硅薄 / VMA 涓殑鎸囬拡鐩磋揪 address_space銆?
---

## flusher 鐨勫鐞嗗崟浣嶆槸鑴?inode 杩樻槸鑴?page锛?
**璋冨害鍗曚綅鏄剰 inode锛屾墽琛屽崟浣嶆槸鑴忛〉銆?*

```
s_dirty 閾捐〃锛?  inode #42锛堣皟搴﹀崟浣嶏級
    鈹溾攢 椤礫0] 鑴?鈫?writepage() 锛堟墽琛屽崟浣嶏級
    鈹溾攢 椤礫2] 鑴?鈫?writepage()
    鈹斺攢 椤礫5] 鑴?鈫?writepage()
  inode #78锛堣皟搴﹀崟浣嶏級
    鈹斺攢 ...
```

| 缁村害 | 绛旀 |
|------|------|
| flusher 浠庨摼琛ㄥ彇浠€涔堬紵 | **鑴?inode**锛坄list_first_entry(&sb->s_dirty, ...)`锛?|
| flusher 瀵逛粈涔堣皟鐢?writepage锛?| **鑴忛〉**锛堥亶鍘?xarray 鑴忔爣绛撅級 |
| 閾捐〃鑺傜偣鏄粈涔堬紵 | **inode**锛坄inode->i_dirty_list`锛?|
| "涓€涓剰椤?鑳借Е鍙?inode 鍏ラ摼鍚楋紵 | **鑳?*锛坄mark_buffer_dirty()` 棣栨鏍囪鑴忛〉鏃跺叆閾撅級 |

涓轰粈涔堜互 inode 涓哄崟浣嶏紵鍥犱负鍚屼竴涓?inode 鐨勬暟鎹潡鍦ㄧ鐩樹笂閫氬父杩炵画鈥斺€斾竴娆℃€у洖鍐欒兘鏈€澶у寲纾佺洏鍚炲悙銆?
---

## flusher 閬嶅巻 xarray 鏃朵細纰板埌骞插噣椤靛悧锛?
**涓嶄細銆?* xarray 鏀寔**鏍囩閬嶅巻锛坱agged iteration锛?*鈥斺€擿find_get_folio_tag(XA_TAG_DIRTY)` 鍙繑鍥炴湁鑴忔爣绛剧殑椤点€傚簳灞傜敤鐨勬槸鍩烘暟鏍戣妭鐐逛笂鐨勬爣绛句綅鍥撅紝鍙煡鏈夋爣绛剧殑瀛愭爲锛岃繛"鐪嬩竴鐪煎共鍑€椤?鐨勫紑閿€閮芥病鏈夈€?
> 鏃╂湡鍐呮牳锛?.6.x 涔嬪墠锛夋病鏈夋爣绛鹃亶鍘嗭紝flusher 纭疄浼氶亶鍘?inode 鐨勬墍鏈夐〉閫愪釜妫€鏌?`PageDirty()`銆?
---

## kswapd 涓?flusher 鐨勫伐浣滄柟寮忓姣?
```
flusher锛?             kswapd锛?  璧风偣 鈫?鑴?inode 閾捐〃      璧风偣 鈫?鐗╃悊椤?LRU 閾捐〃
    鈫?閬嶅巻鑴忛〉锛坸array 鏍囩锛?  鈫?閬嶅巻鐗╃悊椤垫
    鈫?鍐欏洖纾佺洏                 鈹溾攢 骞插噣鏂囦欢椤?鈫?鐩存帴閲婃斁
    鈫?涓嶇 VMA/椤佃〃            鈹斺攢 鑴忔枃浠堕〉 鈫?writeback + 娓呴〉琛?                                鈹斺攢 鍖垮悕椤?鈫?鎹㈠嚭鍒?swap
```

| 缁村害 | flusher | kswapd |
|------|---------|--------|
| **璧风偣** | 鑴?inode 閾捐〃 | 鐗╃悊椤?LRU 閾捐〃 |
| **鍏冲績浠€涔?* | "鍝簺鏂囦欢鏈夎剰椤垫病鍐欏洖" | "鍝簺鐗╃悊椤靛彲浠ヨ鍥炴敹" |
| **鍐欒剰椤?* | 鉁?涓昏宸ヤ綔 | 鈿狅笍 涓轰簡鍥炴敹椤垫鎵嶅仛 |
| **娓呯悊椤佃〃** | 鉂?涓嶅仛 | 鉁?`try_to_unmap()` |
| **瑙﹀彂鏉′欢** | 鏃堕棿/姣斾緥鍒版湡 | 鍐呭瓨鍘嬪姏 |

flusher 鏄?浠庝笂寰€涓?鈥斺€斾粠 inode 鍑哄彂鎵捐剰椤垫潵鍐欙紱kswapd 鏄?浠庝笅寰€涓?鈥斺€斾粠鐗╃悊椤靛嚭鍙戯紝鍙戠幇鏄剰鏂囦欢椤靛氨鍐欏洖+娓呴〉琛紝鐩殑鏄吘鍑哄唴瀛樸€?
---

## flusher 涓轰粈涔堜笉鐢ㄧ椤佃〃锛?
鍥犱负 **flusher 鐨勭洰鏍囨槸鎶婅剰鏁版嵁鎸佷箙鍖栧埌纾佺洏锛屼笉閲婃斁椤垫銆?*

```
flusher锛氬彧鍐?dirty
  鈫?鍐欏畬鍚庨〉鍙樺共鍑€
  鈫?椤垫浠嶇劧鍦?page cache 涓?  鈫?椤佃〃椤逛粛鐒舵湁鏁?  鈫?杩涚▼涓嬫璇诲悓涓€椤?鈫?鐩存帴鍛戒腑 鉁?
kswapd锛氳閲婃斁鐗╃悊椤垫
  鈫?鍏堢‘淇濇暟鎹凡鎸佷箙鍖栵紙鍐?dirty锛?  鈫?鍐嶉噴鏀鹃〉妗?鈫?椤垫褰掕繕 buddy allocator
  鈫?蹇呴』娓呴〉琛?鈫?鍚﹀垯杩涚▼璁块棶鏃?MMU 鏄犲皠鍒板凡琚洖鏀剁殑椤垫
  鈫?杩涚▼涓嬫璇?鈫?缂洪〉 鈫?浠庣鐩橀噸鏂板姞杞?鉂?```

鏍稿績锛氶〉琛ㄦ槧灏勭殑鏄?*鐗╃悊椤垫**锛屼笉鏄鐩樻暟鎹€俧lusher 涓嶇椤垫鍙鏁版嵁锛屾墍浠ラ〉琛ㄤ笉闇€瑕佸姩锛沰swapd 瑕佸洖鏀堕〉妗嗭紝蹇呴』鍏堟竻椤佃〃銆?
---

## flusher 鍜?kswapd 濡備綍澶勭悊鍚屼竴涓?page cache锛?
閫氳繃涓夊眰鏍囧織浣嶄繚鎶わ細

| 鏍囧織浣?| 浣滅敤 | 璋佺敤瀹?|
|--------|------|--------|
| `PG_locked` | 淇濇姢椤垫暟鎹笉琚苟鍙戜慨鏀?| write() 璺緞淇敼椤垫椂鍔犻攣 |
| `PG_dirty` | 鏍囪椤甸渶瑕佸洖鍐?| write() 璁剧疆锛屽洖鍐欏畬鎴愬悗娓呴櫎 |
| `PG_WRITEBACK` | 澹版槑"I/O 姝ｅ湪杩涜" | 闃叉 flusher 鍜?kswapd 閲嶅鍥炲啓 |

娴佺▼锛?
```
flusher                          kswapd
  鈹?                               鈹?  鈹溾攢 folio_test_set_writeback()    鈹溾攢 folio_test_set_writeback()
  鈹?  杩斿洖 false锛堝厛璁剧疆鎴愬姛锛?     鈹?  杩斿洖 true锛堝凡琚缃級
  鈹?                               鈹?  鈹溾攢 writepage() 鈫?I/O             鈹溾攢 folio_wait_writeback(folio)
  鈹?  鈥︹€?纾佺洏鍐欏洖涓?鈥︹€?            鈹?  绛?  鈹?                               鈹?  鈹溾攢 folio_end_writeback()         鈹?  鈹?  鈫?鍞ら啋绛夊緟鑰?鈫愨攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹尖攢鈹€ 閱掓潵
  鈹?                               鈹?  鈹斺攢 缁х画涓嬩竴涓?node               鈹溾攢 椤靛彉骞插噣浜?鈫?姝ｅ父鍥炴敹
                                    鈹斺攢 try_to_unmap() 鈫?娓呴〉琛?```

```c
if (folio_test_set_writeback(folio)) {
    // 鍒汉宸茬粡鍦ㄥ啓鍥炰簡锛屾垜涓嶉渶瑕佸仛
    folio_wait_writeback(folio);
    return;  // 闆?I/O
}
// 鍙湁鎴戣兘鍋?I/O
mapping->a_ops->writepage(folio, wbc);
folio_end_writeback(folio);  // 娓呮爣蹇楋紝鍞ら啋绛夊緟鑰?```

---

*鏈€鍚庢洿鏂帮細2025-06-25*

---

## 纾佺洏 inode bitmap 鍜?inode table 鏁伴噺涓€鑷村悧锛?
**瀹屽叏涓€鑷淬€?* bitmap 鐨勭 N 浣?鈫?table 涓殑绗?N 涓?inode 鈥斺€?涓€涓€瀵瑰簲銆?
inode bitmap 鏄竴涓?4KB 鐨勫潡锛屾瘡涓?bit 琛ㄧず涓€涓?inode 鏄惁琚崰鐢ㄣ€傛瘡涓潡缁勪腑 bitmap 鍙敤鍓?`inodes_per_group` 涓?bit锛堝 8192锛夛紝鍓╀綑鐨勬槸 padding銆俰node table 鍒欒繛缁瓨鏀惧搴旀暟閲忕殑 inode 鏉＄洰锛?56B 脳 8192 = 512 涓潡锛夈€?
**涓轰粈涔?inode 鎬绘暟鍦?mkfs 鏃跺畾姝伙紵** 鍥犱负 bitmap 鍜?table 鍦ㄦ牸寮忓寲鏃跺氨宸茬粡鍒嗛厤濂戒綅缃拰澶у皬浜嗭紝涔嬪悗涓嶈兘鍔ㄦ€佹墿鍏呫€?
---

## 闂存帴鍧椾腑鐨勫潡鍙锋槸椤哄簭鎺掑垪鐨勫悧锛?
**鏄殑锛屼弗鏍兼寜鐓ф枃浠堕€昏緫鍧楀彿鐨勯『搴忔帓鍒椼€?*

- `i_block[0]` = 閫昏緫鍧?0锛宍i_block[1]` = 閫昏緫鍧?1锛?..锛宍i_block[11]` = 閫昏緫鍧?11
- 闂存帴鍧楋紙`i_block[12]` 鎸囧悜鐨勫潡锛夛細閲岄潰 1024 涓潡鍙锋寜椤哄簭瀵瑰簲閫昏緫鍧?12~1035
- 浜岀骇闂存帴锛氬垎灞傜殑閫昏緫鍧楁槧灏勶紝姣忓眰閮芥槸涓€涓繛缁潡鍙锋暟缁?
鎵€浠ユ牴鎹€昏緫鍧楀彿鍙互蹇€熻绠楀畠鍦ㄥ摢涓€绾ч棿鎺ャ€佺鍑犱釜浣嶇疆鈥斺€旇繖涔熸槸 ext2/ext3 闅忔満璁块棶澶ф枃浠舵椂鎱㈢殑鍘熷洜涔嬩竴锛氳璇诲娆￠棿鎺ュ潡鎵嶈兘鎵惧埌鐩爣鐗╃悊鍧楀彿銆?
---

## Extent 鏍硅妭鐐瑰湪 i_block[15] 涓殑鍝釜浣嶇疆锛?
**鏄暣涓?i_block[15] 鏁扮粍锛?0 瀛楄妭锛夛紝涓嶆槸鏌愪釜鍏冪礌銆?*

褰?inode 璁剧疆浜?`EXT4_EXTENTS_FL` 鏍囧織鏃讹紝60 瀛楄妭鐨勮涔夊畬鍏ㄦ敼鍙樷€斺€斾笉鍐嶈褰撲綔 15 涓?4 瀛楄妭鍧楀彿锛岃€屾槸琚暣浣撳鐢ㄤ负锛?
```
i_block[0..14] = 60 瀛楄妭锛?  ext4_extent_header (12 瀛楄妭)
    eh_magic=0xF30A, eh_entries, eh_max=4, eh_depth
  ext4_extent[0] (12 瀛楄妭)  鈫?绗竴涓?extent 鏉＄洰
  ext4_extent[1] (12 瀛楄妭)
  ext4_extent[2] (12 瀛楄妭)
  ext4_extent[3] (12 瀛楄妭)
```

- **4 涓?extent 鎴栨洿灏?*锛氭牴鑺傜偣灏辨槸鍙跺瓙锛屽叏閮?60 瀛楄妭灏卞鐢ㄤ簡
- **瓒呰繃 4 涓?extent**锛歚eh_depth > 0`锛屾牴鑺傜偣鍙樻垚绱㈠紩鑺傜偣锛屾寚鍚戝瓙鑺傜偣鎵€鍦ㄧ殑鍧?
澶у鏁版枃浠跺彧闇€瑕佷竴涓?inode 璇诲叆灏辫兘鑾峰彇瀹屾暣鐨勬暟鎹潡鏄犲皠鈥斺€?0 瀛楄妭鐨?`i_block[]` 绌洪棿閲屽凡缁忓寘鍚簡鎵€鏈?metadata銆?
---

## 鐩綍鏂囦欢鐨勫唴瀹规槸浠€涔堬紵ext4_lookup() 鍋氫粈涔堬紵

鐩綍鏄竴涓?*鐗规畩绫诲瀷鐨勬枃浠?*锛屽畠鐨勬暟鎹潡閲屽瓨鍌ㄧ殑鏄粨鏋勫寲鐨?鐩綍椤?璁板綍鈥斺€旀瘡涓潯鐩氨鏄竴涓?鏂囦欢鍚嶁啋inode 鍙?鐨勬槧灏勩€?
```
鐩綍椤圭粨鏋勶細
  [inode=45] [rec_len=12] [name_len=4] [type=2] "home"
  [inode=78] [rec_len=12] [name_len=4] [type=1] "doc.txt"
```

**ext4_lookup(dir_inode, "doc.txt")**锛氭帴鏀剁埗鐩綍鐨?inode锛岃瀹冪殑鐩綍鏂囦欢鏁版嵁鍧楋紝鍦ㄥ叾涓『搴忔壂鎻忕洰褰曢」鍖归厤鏂囦欢鍚嶏紝杩斿洖瀛愭枃浠?鐩綍鐨?inode 鍙枫€?
---

## 椤哄簭鎵弿鏄粈涔堣寖鍥达紵浠庢牴鐩綍寮€濮嬪悧锛?
**涓嶆槸浠庢牴鐩綍閬嶅巻鏁翠釜鏂囦欢绯荤粺銆?* 鍙悳绱㈣矾寰勪笂**姣忎竴绾х洰褰曡嚜韬殑**鍐呭銆?
鏌ユ壘 /home/user/doc.txt 鐨勮繃绋嬶細
1. 璇绘牴鐩綍 inode(#2) 鐨勬暟鎹潡 鈫?椤哄簭鎵弿鎵?"home" 鈫?寰楀埌 inode #45
2. 璇?inode(#45) 鐨勬暟鎹潡锛?home 鐩綍锛?鈫?椤哄簭鎵弿鎵?"user" 鈫?寰楀埌 inode #106
3. 璇?inode(#106) 鐨勬暟鎹潡锛?home/user 鐩綍锛?鈫?椤哄簭鎵弿鎵?"doc.txt" 鈫?寰楀埌 inode #1089

灏卞儚浣犳墦寮€涓€涓枃浠跺す锛堜綘鐭ラ亾瀹冨湪鍝級锛岀劧鍚庡湪閲岄潰瀵圭潃鍒楄〃鎵句綘瑕佺殑鏂囦欢鈥斺€?椤哄簭鎵弿"鍙拡瀵瑰綋鍓嶆墦寮€鐨勮繖涓€涓枃浠跺す鐨勫唴瀹广€?
---

## ext4 delalloc 鎵归噺鐢宠澶辫触浼氭€庝箞鏍凤紵

杩欐槸 delalloc 鐨勬渶澶ч闄╋細

- **ext3**锛歸rite() 鏃跺氨鍒嗛厤纾佺洏鍧楋紝绔嬪嵆鐭ラ亾鎴愯触銆傚垎閰嶅け璐?鈫?write() 杩斿洖 ENOSPC
- **ext4**锛歸rite() 鍙啓 page cache锛岃繑鍥炴垚鍔熴€傚洖鍐欐椂鎵归噺鎵惧潡锛屽鏋滃け璐?鈫?鏁版嵁涓㈠け锛堝彧鍦?page cache 閲岋紝浠庢湭鍒嗛厤纾佺洏鍧楋級

**濡傛灉宸茬粡鏈夌鐩樺潡鐨勬枃浠跺仛淇+杩藉姞鍐?*锛?- 鏃ф暟鎹潡涓嶅彉锛堣鐩栧凡鏈?block锛?- 鏂拌拷鍔犻儴鍒嗕竴娆″垎閰嶈繛缁柊 block
- 鏃ч儴鍒嗗拰杩藉姞閮ㄥ垎鍚勮嚜鍐呴儴杩炵画锛屼簰鐩镐笉闇€瑕佽繛缁?- extent 鏍戠敤澶氫釜鏉＄洰鎻忚堪鏁翠綋甯冨眬

---

## htree锛堝搱甯屾爲锛夋槸浠€涔堢粨鏋勶紵

htree 鏄竴妫?*鍩轰簬鍝堝笇鍊肩殑 B 鏍戝彉浣?*锛屼笓涓哄姞閫熺洰褰曟煡鎵捐璁°€?
**鏍稿績鎬濇兂**锛氭妸鏂囦欢鍚嶅搱甯屽悗锛屾寜鍝堝笇鍊艰寖鍥村垎妗讹紙bucket锛夛紝姣忎釜妗舵槸涓€涓暟鎹潡銆?
```
鐩綍鏂囦欢绗?0 鍧楋紙绱㈠紩鍧楋級锛?  dx_root_info 鈫?hash_version, tree_height
  htree 绱㈠紩鑺傜偣锛?    [hash=0x0000, block=1]   鈫?鍝堝笇鍊?0x0000~0x3FFF 鐨勬潯鐩湪鍧?1
    [hash=0x4000, block=2]   鈫?鍝堝笇鍊?0x4000~0x7FFF 鐨勬潯鐩湪鍧?2
    [hash=0x8000, block=3]
    [hash=0xC000, block=4]
```

**鏌ユ壘杩囩▼**锛?1. 璁＄畻 hash("doc.txt") = 0x1234
2. 鍦ㄧ储寮曞潡浜屽垎鏌ユ壘 鈫?钀藉湪鍖洪棿 0x0000~0x3FFF 鈫?鍘绘暟鎹潡 1
3. 鍦ㄦ暟鎹潡 1 涓簩鍒嗘煡鎵撅紙鏉＄洰鎸夊搱甯屾帓搴忥級鈫?鎵惧埌 "doc.txt"

**鎬诲鏉傚害 O(log N) 鑰屼笉鏄?O(N)**銆傛病鏈?htree 鏃讹紝10 涓囦釜鏂囦欢鐨勭洰褰曢渶瑕侀亶鍘嗘墍鏈?10 涓囦釜鏉＄洰銆?
---

*鏈€鍚庢洿鏂帮細2025-06-25*

---

## 鏃ュ織鍐欏叆瀵瑰簲鐢ㄧ▼搴忕殑寤惰繜鍙鍚楋紵

**鍙栧喅浜庢槸鍚﹁皟鐢?fsync()銆?*

- **write() 璺緞**锛氭暟鎹埌 page cache锛屽鏋滀慨鏀逛簡鍏冩暟鎹細璋冪敤 `journal_start()`锛屾棩蹇楃┖闂村揩婊℃椂鍙兘鐭殏闃诲锛堝井绉掔骇锛夛紝鍩烘湰鏃犳劅鐭?鉁?- **fsync() 璺緞**锛氬繀椤荤瓑寰呮棩蹇椾簨鍔℃彁浜ゅ畬鎴愶紙娑夊強 I/O 鍐欐弿杩板潡鈫掑厓鏁版嵁鈫掓彁浜ゅ潡锛夛紝寤惰繜瀹屽叏鍙 鉂?
鏁版嵁搴擄紙濡?PostgreSQL锛夊ぇ閲忎娇鐢?fsync锛屾墍浠ュ纾佺洏鐨?fsync 鎬ц兘鏋佸叾鏁忔劅鈥斺€旀湰璐ㄥ氨鏄湪绛?journal commit銆?
---

## 鏃ュ織婊′簡浼氭€庝箞鏍凤紵

涓嶅悓妯″紡涓嬫棩蹇楁秷鑰椾笉鍚岋細

| 妯″紡 | 鍐?4KB 鏁版嵁鐨勬棩蹇楁秷鑰?|
|------|:-:|
| ordered | ~1KB锛堝彧璁?inode/bitmap 鍏冩暟鎹級|
| writeback | ~1KB锛堝悓涓婏級|
| journal | 4KB + ~1KB = ~5KB锛堟暟鎹厛杩涙棩蹇楋級|

婊′簡涔嬪悗锛歚journal_start()` 闃诲锛岀瓑寰?checkpoint 鍥炴敹鏃ュ織绌洪棿銆傝繖涓樆濉炲搴旂敤绋嬪簭鍙鈥斺€攚rite() 浼氬崱浣忥紝鐩村埌鏃ュ織绌洪棿琚洖鏀躲€傞粯璁ゆ棩蹇楀ぇ灏忛€氬父 128MB锛宱rdered 妯″紡涓嬫櫘閫氳礋杞藉緢灏戞拺婊°€?
**鏃ュ織涓嶆槸纾佺洏涓婄殑涓€娈电嫭绔嬬┖闂达紝瀹冩槸鐜舰缂撳啿鍖恒€?* 鏃ュ織澶存寚鍚戞柊浜嬪姟鍐欏叆鐨勪綅缃紝鏃ュ織灏炬寚鍚戝凡 checkpoint 瀹屾垚鐨勪綅缃€傚ご杩戒笂灏惧氨婊′簡銆?
---

## ordered 妯″紡鐨勫畨鍏ㄧ己鍙ｂ€斺€?鍐欎簡鐨勬暟鎹笉涓€瀹氳寮曠敤"

杩欐槸涓€涓潪甯告繁鍒荤殑闂銆?
ordered 妯″紡鐨勫畬鏁?fsync 鍐欏叆娴佺▼锛?```
姝ラ A锛氭暟鎹潡鍐欏叆鐩爣浣嶇疆      鉁?鏁版嵁鍦ㄧ鐩?姝ラ B锛氭弿杩板潡 + inode 鍐欏叆鏃ュ織 鉁?鍏冩暟鎹湪鏃ュ織
姝ラ C锛氭彁浜ゅ潡                  鈴?鍘熷瓙鏍囪

濡傛灉鍦ㄦ楠?C 涔嬪墠宕╂簝锛?  鈫?鏃ュ織鎵弿锛氭湁鎻忚堪鍧?+ 鍏冩暟鎹紝浣嗘病鏈夋彁浜ゅ潡
  鈫?缁撹锛氫笉瀹屾暣浜嬪姟 鈫?涓㈠純
  鈫?inode 鎭㈠涓烘棫鍊硷紝bitmap 鎭㈠涓烘棫鍊?  鈫?鏁版嵁鍧楀凡缁忓湪纾佺洏涓婁簡 鉁咃紝浣?inode 涓嶆寚鍚戝畠 鉂?  鈫?bitmap 鏍囦负"绌洪棽" 鈫?鍚庣画鍙兘琚鐩?鈫?鏁版嵁涓㈠け
```

**ordered 妯″紡淇濊瘉鐨勬槸"寮曠敤鐨勬暟鎹竴瀹氭湁鏁?锛屼笉鏄?鍐欎簡鐨勬暟鎹竴瀹氳寮曠敤"銆?*

- 鉁?濡傛灉 inode 閫氳繃鏃ュ織鎭㈠鎸囧悜浜嗕竴涓暟鎹潡 鈫?杩欎釜鏁版嵁鍧椾竴瀹氬凡缁忓啓濂戒簡
- 鉂?濡傛灉鏁版嵁鍧楀凡缁忓啓濂戒簡 鈫?inode 涓嶄竴瀹氭寚鍚戜簡瀹?
杩欏氨鏄?fsync 鐨勪綔鐢細瀹冭搴旂敤绋嬪簭鐭ラ亾"鎴愬姛浜嗚繕鏄け璐ヤ簡"銆傚鏋?fsync 宕╂簝浜嗭紝娌¤繑鍥炴垚鍔?鈫?搴旂敤绋嬪簭鍙互閲嶈瘯銆傛暟鎹€愪箙鎬х殑鏈€缁堣矗浠诲湪搴旂敤绋嬪簭鈥斺€斿繀椤绘鏌?fsync 鐨勮繑鍥炲€笺€?
---

## 鏃ュ織涓彧鍖呭惈鍏冩暟鎹悧锛?
**涓嶅畬鍏ㄦ槸鈥斺€斿彇鍐充簬鏃ュ織妯″紡銆?*

| 妯″紡 | 鏃ュ織涓寘鍚?|
|------|-----------|
| ordered | 鉁?鍙湁鍏冩暟鎹紙inode銆乥itmap銆乪xtent 鏍戯級 |
| writeback | 鉁?鍙湁鍏冩暟鎹?|
| journal | 鈿狅笍 鍏冩暟鎹?+ 鏂囦欢鏁版嵁閮借繘鏃ュ織 |

ordered 妯″紡涓嬶紝鏃ュ織閲屽彧鏈?inode銆乥itmap銆乪xtent 鏍戠瓑鍏冩暟鎹殑"鍓湰"銆傛枃浠跺唴瀹圭洿鎺ュ啓鍒版暟鎹尯锛屼笉杩涙棩蹇椼€傛棩蹇楀彧淇濇枃浠剁郴缁熺粨鏋勭殑涓€鑷存€э紝涓嶄繚鏂囦欢鍐呭銆?
data=journal 妯″紡涓嬫暟鎹篃鍐欐棩蹇楋紝鎵€浠ユ瘡涓暟鎹潡琚啓涓ゆ锛堜竴娆℃棩蹇椼€佷竴娆＄洰鏍囦綅缃級锛屽啓鏀惧ぇ涓ラ噸锛屾棩蹇椾篃鏇村鏄撶垎婊°€?
---

## data=journal 鍐欏ぇ鏂囦欢鏃ュ織浼氱垎婊″悧锛?
**浼氾紝浣嗕笉浼氭寕鈥斺€斿皬绠￠亾鎸佺画鎼按銆?*

鏃ュ織鍍忎竴涓?128MB 鐨勮浆鍌ㄥ甫锛?```
鈶?鍐?128MB 鈫?鏃ュ織婊′簡
鈶?瑙﹀彂 checkpoint锛氭妸鏁版嵁浠庢棩蹇楀洖鏀惧埌鐩爣鏁版嵁鍖?鈶?鍥炴斁瀹屾垚 鈫?128MB 鏃ュ織绌洪棿閲婃斁
鈶?缁х画鍐欐柊鐨?128MB 鍒版棩蹇?...
鈶?鍙嶅 8 娆★紝鍐欏畬 1GB
```

**浠ｄ环**锛氭暟鎹鍐欎簡涓ゆ锛堟棩蹇?+ 鐩爣浣嶇疆锛夛紝鍔犱笂 checkpoint 寮曡捣鐨勯澶栧紑閿€銆傝繖灏辨槸 data=journal 鎱㈢殑鏍规湰鍘熷洜銆?
宸ョ▼鏁欒锛氭暟鎹簱閫氬父涓嶇敤 data=journal 妯″紡锛圥G/MySQL 鏈夎嚜宸辩殑 WAL锛夈€俤ata=journal 鏇撮€傚悎灏戦噺灏忔枃浠跺啓鍏ョ殑妗岄潰/宓屽叆寮忓満鏅€?
---

## ordered 鍜?writeback 鐨勬牳蹇冨尯鍒?
**涓€鍙ヨ瘽锛歰rdered 瑕佹眰鏁版嵁鍧楀厛鍒扮鐩橈紝鍏冩暟鎹棩蹇楀啀鎻愪氦銆倃riteback 涓嶅仛杩欎釜淇濊瘉銆?*

```
ordered:    鏁版嵁鍧楀厛鍒扮鐩?鉁?鈫?鍏冩暟鎹棩蹇楁彁浜?鉁?writeback:  鏁版嵁鍧椾粈涔堟椂鍊欏埌閮借 鈫?鍏冩暟鎹棩蹇楃洿鎺ユ彁浜?```

writeback 宕╂簝鍚庣殑椋庨櫓锛?```
鍏冩暟鎹棩蹇楁彁浜?鉁咃紙inode: "鏁版嵁鍦?block #5000"锛?鏁版嵁鍧楄繕娌″啓 鈴?鈫?宕╂簝 馃拃
鎭㈠鍚?鈫?inode 鎸囧悜 block #5000 鈫?閲岄潰鏄瀮鍦?鉂?```

| | ordered | writeback |
|---|---|---|
| 鍏冩暟鎹畨鍏?| 鉁?| 鉁?|
| 鏁版嵁鍐呭姝ｇ‘ | 鉁?宕╂簝涓嶅嚭鐜颁贡鐮?| 鈿狅笍 宕╂簝鍙兘璇诲埌鍨冨溇 |
| 鎬ц兘 | 姝ｅ父 | 鐣ュソ 5-10%锛圛/O 璋冨害鍣ㄦ洿鑷敱锛?|

ordered 鏄粯璁ゆā寮忊€斺€斿鑺变竴鐐规€ц兘鎹?宕╂簝鍚庢枃浠跺唴瀹逛笉鍧?鐨勪繚闅溿€倃riteback 鍙敤浜庢槑纭笉鍏冲績鏁版嵁鎸佷箙鎬х殑鍦烘櫙锛堝涓存椂鍒嗗尯锛夈€?
---

*鏈€鍚庢洿鏂帮細2025-06-25*
---

## procfs 璇荤紦鍐插尯濡備綍淇濊瘉澶у皬瓒冲锛?
procfs 浣跨敤鍐呮牳鐨?**seq_file 鏈哄埗**锛岀紦鍐插尯鑷姩鎵╁锛?
1. 鍒濆鍒嗛厤 PAGE_SIZE锛?KB锛夌紦鍐插尯
2. 鏍煎紡鍖栧嚱鏁板線缂撳啿鍖哄啓鍐呭锛屽鏋滃啓婊′簡 鈫?seq_file 鑷姩鍔犲€嶏紙8KB銆?6KB銆?2KB...锛?3. 浠庡ご閲嶆柊鏍煎紡鍖栵紝鐩村埌缂撳啿鍖哄鐢ㄤ负姝?
瀵逛簬 `/proc/self/status` 绛夊凡鐭ュぇ灏忕殑鏂囦欢锛?KB 涓€娆″氨澶熶簡銆傚浜?`/proc/self/maps` 绛夊彲鑳藉緢澶х殑鏂囦欢锛宻eq_file 鑷姩鎵╁銆?
---

## procfs 鐨?inode 浠€涔堟椂鍊欏垱寤猴紵

**涓嶆槸杩涚▼鍒涘缓鏃堕鍒涘缓鐨勶紝鑰屾槸 lookup() 鏃舵寜闇€鐢熸垚銆?*

- **/proc 涓嬬殑鍥哄畾鏂囦欢**锛坴ersion銆乧puinfo锛夛細鎸傝浇鏃舵敞鍐?proc_dir_entry锛屼絾 inode 绗竴娆¤闂椂鎵嶉€氳繃 proc_lookup() 鍒涘缓
- **/proc/\<pid\>/ 涓嬬殑鏂囦欢**锛坰tatus銆乫d銆乵aps锛夛細璁块棶鏃跺姩鎬佸垱寤?
```
璁块棶 /proc/1234/status 鐨勮繃绋嬶細
  鈶?瑙ｆ瀽 "1234" 鈫?proc_lookup() 琚皟鐢?     鈫?鍦?task 閾捐〃鎵?PID=1234 鈫?鍒涘缓 inode锛坕node鍙?= PID锛?  鈶?瑙ｆ瀽 "status" 鈫?proc_lookup() 琚皟鐢?     鈫?鍦?proc_dir_entry 鏍戜腑鎵惧埌 "status" 鈫?鍒涘缓 inode
     鈫?f_op->read = proc_pid_status
```

proc_lookup() 鍦?dcache 鏈懡涓椂琚?VFS 璋冪敤鐨?lookup_slow() 瑙﹀彂锛岀涓€娆¤闂悗 dentry 缂撳瓨涓嬫潵灏变笉鍐嶈皟浜嗐€?
---

## sysfs 璇绘搷浣滆兘鐩存帴璁块棶鍐呮牳鏁版嵁鐨勬牴鏈師鍥?
**姝ｇ‘銆傚洜涓?read() 绯荤粺璋冪敤闄峰叆鍐呮牳鎬侊紝CPU 鍦ㄥ唴鏍哥壒鏉冪骇杩愯锛屽唴鏍镐唬鐮佸彲浠ョ洿鎺ヨВ寮曠敤浠讳綍鍐呮牳鍐呭瓨鍦板潃銆?*

```
read("/sys/class/net/eth0/statistics/rx_bytes", buf, 32)
  鈫?绯荤粺璋冪敤 鈫?鍐呮牳鎬?  鈫?sysfs read 瀹炵幇鐩存帴璇诲彇 struct net_device 涓殑 rx_bytes 瀛楁
  鈫?鏍煎紡鍖栧悗 copy_to_user(buf)
  鈫?杩斿洖鐢ㄦ埛鎬?```

涓嶉渶瑕?page cache锛屼笉闇€瑕佺鐩?I/O鈥斺€斿氨鏄竴涓唴瀛樿鍙栨搷浣溿€傝繖鏄墍鏈夎櫄鎷熸枃浠剁郴缁熺殑鍏辨€с€?
---

## tmpfs 鎹㈠嚭鍒?swap 鍚庯紝瑕佷笉瑕佹洿鏂扮鐩樹笂鐨?inode锛?
**涓嶉渶瑕併€傚洜涓?swap 涓嶆槸涓€涓枃浠剁郴缁燂紝娌℃湁 inode 鐨勬蹇点€?*

Swap 鍒嗗尯鏄竴涓?骞抽潰"鐨勫浐瀹氬ぇ灏忔Ы浣嶏紙slot锛夋暟缁勶紝姣忎釜妲戒綅 4KB锛?
```
swap 鍒嗗尯甯冨眬锛?  鈹屸攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹?  鈹?swap 瓒呯骇鍧?          鈹?鈫?鏍囪瘑杩欐槸 swap 鍒嗗尯
  鈹溾攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹?  鈹?swap slot 0: [鏁版嵁]  鈹?鈫?娌℃湁 inode
  鈹?swap slot 1: [鏁版嵁]  鈹?鈫?娌℃湁鐩綍椤?  鈹?swap slot 2: [绌洪棽]  鈹?鈫?娌℃湁鏂囦欢鍚?  鈹?...                  鈹?  鈹斺攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹?```

鏄犲皠鍏崇郴涓嶅湪 inode 涓紝鑰屽湪涓や釜鍦版柟锛?- **PTE锛堥〉琛ㄩ」锛?*锛氭崲鍑烘椂璁板綍 `swap_entry_t`锛堢紪鐮佷簡"鍝釜 swap 璁惧 + 鍝釜妲藉彿"锛?- **struct page**锛歱age->private 璁板綍 swap_entry_t锛屾崲鍏ユ椂鐢ㄨ繖涓壘鍥炴潵

鍏抽敭鍖哄埆锛?```
ext4 璇绘暟鎹細   鏂囦欢鍋忕Щ 鈫?inode 鈫?extent 鏍?鈫?鐗╃悊鍧楀彿 鈫?BIO
tmpfs 鎹㈠叆锛?   PTE 鈫?swap_entry_t 鈫?璁惧+妲藉彿 鈫?BIO
                        鈫?              涓嶇粡杩?VFS锛屾病鏈?inode锛?```

tmpfs 鐨?inode 鏈韩涔熷彧鍦ㄥ唴瀛樹腑锛坰lab 鍒嗛厤鍣級锛屼粠鏈啓鍏ョ鐩樸€傞噸鍚悗 PTE 鍜?inode 閮戒涪澶憋紝鍗充娇 swap 鏁版嵁杩樺湪涔熸棤娉曞叧鑱斻€?
---

*鏈€鍚庢洿鏂帮細2025-06-25*