Есть какаято странная ситуация, описать вы ее**не можете**корректно.

Что надо предоставить суппорту,чтоб было понятно, в чем собственно дело?

1\) ждете вечера или любого другого времени, когда никто не использует атс.

2\) заходите по ssh на машину.если доступа нет, то[как настроить](http://redhat-club.org/2011/%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-%D0%B8-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-openssh-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%B0-%D0%B2-rhel-centos-fedora)[как зайти](http://dmitrykhn.homedns.org/wp/2009/02/putty-console-to-linux-from-windows/)

3\) вводите

```
asterisk 
-
rvvvv


```

4\) звоните

5\) записываете что вывалилось на екран. в путти это делается правой кнопкой мышки. копирум в вопрос\(ctrl-v\), выделяем логи в вопросе[через ctrl-K](http://asterisk-support.ru/faq/).

---

если не помогло понять, то**уровень два**.

```
asterisk 
-
rvvvv


sip 
set
 debug on


```

---

если не помогло, и есть скрипты AGI/fastagi -**уровень 3**

```
asterisk 
-
rvvvvv


sip 
set
 debug on


agi 
set
 debug on


```

---

если не помогло, или**совсем все запутано**. сначала думаете,стоит ли продолжать. ибо желающих бесплатно читать дебаг - чуть менее чем нисколько.

редактируете /etc/asterisk/logger.conf\( если freepbx то logger_logfiles_custom.conf\)

чтоб стала вот такая строчка

```
console 
=
>
 notice
,
warning
,
error
,
debug
,
dtmf


```

перегружаете астериск

```
asterisk 
-
vvvvgc


sip 
set
 debug on


core 
set
 debug 
5


agi 
set
 debug on


```

опционально \(если странные проблемы с dtmf\)

```
dtmf debug on


```

---

предварительно можно почитать

[asterisk debug](http://www.voip-info.org/wiki/view/Asterisk+debugging)

[The Future Of Telephony](http://www.google.com.ua/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=0CCEQFjAA&url=http%3A%2F%2Fwww.asteriskdocs.org%2F&ei=-ANqUPW9NuWI4gSnrYGoCg&usg=AFQjCNFwn8zDB58pgVUHBHeX9xEs4mzvDw&sig2=ii9-iGSfB4KMHIKruXCDpQ&cad=rja)

[http://asterisk-support.ru/question/14859/knigi-po-asterisk](http://asterisk-support.ru/question/14859/knigi-po-asterisk)/

