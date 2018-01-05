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
ms.workload: dotnet
ms.openlocfilehash: 4bdfa1a9e45332e8c2acbbc8cd8a09bd2f927fbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="8708e-102">Средство поиска закрытых ключей (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="8708e-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="8708e-103">Эта программа командной строки предназначена для извлечения закрытого ключа из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="8708e-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="8708e-104">Например *FindPrivateKey.exe* можно использовать, чтобы найти расположение и имя файла закрытого ключа, связанного с конкретным сертификатом X.509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="8708e-104">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8708e-105">Средство FindPrivateKey поставляется в качестве образца WCF.</span><span class="sxs-lookup"><span data-stu-id="8708e-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="8708e-106">Дополнительные сведения о где найти образец и постройте его. в разделе [FindPrivateKey](./samples/findprivatekey.md).</span><span class="sxs-lookup"><span data-stu-id="8708e-106">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="8708e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8708e-107">Syntax</span></span>

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="8708e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="8708e-108">Remarks</span></span>

<span data-ttu-id="8708e-109">В следующих таблицах описаны аргументы и параметры, которые можно использовать со средством Find Private Key (FindPrivateKey.exe).</span><span class="sxs-lookup"><span data-stu-id="8708e-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="8708e-110">Аргумент</span><span class="sxs-lookup"><span data-stu-id="8708e-110">Argument</span></span>|<span data-ttu-id="8708e-111">Описание</span><span class="sxs-lookup"><span data-stu-id="8708e-111">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="8708e-112">Имя хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="8708e-112">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="8708e-113">Расположение хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="8708e-113">The location of the certificate store.</span></span>|

|<span data-ttu-id="8708e-114">Параметр</span><span class="sxs-lookup"><span data-stu-id="8708e-114">Option</span></span>|<span data-ttu-id="8708e-115">Описание:</span><span class="sxs-lookup"><span data-stu-id="8708e-115">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="8708e-116">`/n <`*subjectName*`>`</span><span class="sxs-lookup"><span data-stu-id="8708e-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="8708e-117">Задает имя субъекта сертификата.</span><span class="sxs-lookup"><span data-stu-id="8708e-117">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="8708e-118">`/t <`*отпечаток*`>`</span><span class="sxs-lookup"><span data-stu-id="8708e-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="8708e-119">Задает отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="8708e-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="8708e-120">Используйте Certmgr.exe для извлечения отпечатка сертификата.</span><span class="sxs-lookup"><span data-stu-id="8708e-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="8708e-121">Выводит только имя файла.</span><span class="sxs-lookup"><span data-stu-id="8708e-121">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="8708e-122">Выводит только каталог.</span><span class="sxs-lookup"><span data-stu-id="8708e-122">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="8708e-123">Выводит абсолютное имя файла.</span><span class="sxs-lookup"><span data-stu-id="8708e-123">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="8708e-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="8708e-124">Examples</span></span>

<span data-ttu-id="8708e-125">Следующая команда извлекает закрытый ключ для John Doe:</span><span class="sxs-lookup"><span data-stu-id="8708e-125">The following command retrieves the private key for John Doe:</span></span>

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="8708e-126">Следующая команда извлекает закрытый ключ для локального компьютера:</span><span class="sxs-lookup"><span data-stu-id="8708e-126">The following command retrieves the private key for the local machine:</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```