---
title: "Средство поиска закрытых ключей (FindPrivateKey.exe)"
ms.date: 09/11/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d515077106b8f0527d045d5ef7fb6d7c0c7aa62
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2017
---
# <a name="find-private-key-tool-findprivatekeyexe"></a>Средство поиска закрытых ключей (FindPrivateKey.exe)

Эта программа командной строки предназначена для извлечения закрытого ключа из хранилища сертификатов. Например *FindPrivateKey.exe* можно использовать, чтобы найти расположение и имя файла закрытого ключа, связанного с конкретным сертификатом X.509 в хранилище сертификатов.

> [!IMPORTANT]
> Средство FindPrivateKey поставляется в качестве образца WCF. Дополнительные сведения о где найти образец и постройте его. в разделе [FindPrivateKey](./samples/findprivatekey.md).

## <a name="syntax"></a>Синтаксис

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a>Примечания

В следующих таблицах описаны аргументы и параметры, которые можно использовать со средством Find Private Key (FindPrivateKey.exe).

|Аргумент|Описание|
|--------------|-----------------|
|`storeName`|Имя хранилища сертификатов.|
|`storeLocation`|Расположение хранилища сертификатов.|

|Параметр|Описание|
|------------|-----------------|
|`/n <`*subjectName*`>`|Задает имя субъекта сертификата.|
|`/t <`*отпечаток*`>`|Задает отпечаток сертификата. Используйте Certmgr.exe для извлечения отпечатка сертификата.|
|`/f`|Выводит только имя файла.|
|`/d`|Выводит только каталог.|
|`/a`|Выводит абсолютное имя файла.|

## <a name="examples"></a>Примеры

Следующая команда извлекает закрытый ключ для John Doe:

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

Следующая команда извлекает закрытый ключ для локального компьютера:

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```