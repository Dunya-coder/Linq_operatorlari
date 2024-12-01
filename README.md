# Linq_operatorlari
```C#
 string[] websites = { "webNameA.com", "webNameB.net",
                      "webNameC.net",
                      "webNameF.org",
                      "webNameI.tv",
                      "webNameD.com",
                      "webNameE.org",
                      "webNameG.tv",
                       "webNameH.net",
                            };
```
Website lar ro'yxati .Agar dastlab oxirgi index!=
Linq so'rovi elon qilinishi:
``` C#
        var webAddrs = from addr in websites
                       where addr.LastIndexOf('.') != -1
                       group addr by
                       addr.Substring(addr.LastIndexOf('.')) into ws
                       where ws.Count() > 2
                       select ws;
        // So'rovni bajarish va uning natijalarini ko'rish. 
        foreach (var sites in webAddrs)
        {
            Console.WriteLine(sites.Key + " domenidagi web saytlar:");
            foreach (var site in sites)
                Console.WriteLine(" " + site);
            Console.WriteLine();
```
