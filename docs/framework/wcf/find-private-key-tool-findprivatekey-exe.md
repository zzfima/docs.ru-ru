---
title: Средство поиска закрытых ключей (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
ms.openlocfilehash: 00ad27d28ee3a589d5ee8702bd036b05d8ceb4b3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637572"
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="7238f-102">Средство поиска закрытых ключей (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="7238f-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="7238f-103">Эта программа командной строки предназначена для извлечения закрытого ключа из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="7238f-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="7238f-104">Например *FindPrivateKey.exe* можно использовать для определения расположения и имя файла закрытого ключа, связанного с конкретным сертификатом X.509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="7238f-104">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7238f-105">Средство FindPrivateKey поставляется в качестве образца WCF.</span><span class="sxs-lookup"><span data-stu-id="7238f-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="7238f-106">Дополнительные сведения о где найти образец и как создавать его, см. в разделе [FindPrivateKey](./samples/findprivatekey.md).</span><span class="sxs-lookup"><span data-stu-id="7238f-106">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="7238f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7238f-107">Syntax</span></span>

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="7238f-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="7238f-108">Remarks</span></span>

<span data-ttu-id="7238f-109">В следующих таблицах описаны аргументы и параметры, которые можно использовать со средством Find Private Key (FindPrivateKey.exe).</span><span class="sxs-lookup"><span data-stu-id="7238f-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="7238f-110">Аргумент</span><span class="sxs-lookup"><span data-stu-id="7238f-110">Argument</span></span>|<span data-ttu-id="7238f-111">Описание</span><span class="sxs-lookup"><span data-stu-id="7238f-111">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="7238f-112">Имя хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="7238f-112">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="7238f-113">Расположение хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="7238f-113">The location of the certificate store.</span></span>|

|<span data-ttu-id="7238f-114">Параметр</span><span class="sxs-lookup"><span data-stu-id="7238f-114">Option</span></span>|<span data-ttu-id="7238f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="7238f-115">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="7238f-116">`/n <` *Имя субъекта* `>`</span><span class="sxs-lookup"><span data-stu-id="7238f-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="7238f-117">Задает имя субъекта сертификата.</span><span class="sxs-lookup"><span data-stu-id="7238f-117">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="7238f-118">`/t <` *отпечаток* `>`</span><span class="sxs-lookup"><span data-stu-id="7238f-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="7238f-119">Задает отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="7238f-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="7238f-120">Используйте Certmgr.exe для извлечения отпечатка сертификата.</span><span class="sxs-lookup"><span data-stu-id="7238f-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="7238f-121">Выводит только имя файла.</span><span class="sxs-lookup"><span data-stu-id="7238f-121">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="7238f-122">Выводит только каталог.</span><span class="sxs-lookup"><span data-stu-id="7238f-122">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="7238f-123">Выводит абсолютное имя файла.</span><span class="sxs-lookup"><span data-stu-id="7238f-123">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="7238f-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="7238f-124">Examples</span></span>

<span data-ttu-id="7238f-125">Следующая команда извлекает закрытый ключ для John Doe:</span><span class="sxs-lookup"><span data-stu-id="7238f-125">The following command retrieves the private key for John Doe:</span></span>

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="7238f-126">Следующая команда извлекает закрытый ключ для локального компьютера:</span><span class="sxs-lookup"><span data-stu-id="7238f-126">The following command retrieves the private key for the local machine:</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```
