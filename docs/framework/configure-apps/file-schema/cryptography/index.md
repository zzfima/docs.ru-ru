---
title: Схема параметров криптографии
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
ms.openlocfilehash: a7964d01905be4e3dd6e8149e5533e9a2cfd9a71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927630"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="92e6b-102">Схема параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="92e6b-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="92e6b-103">Схема параметров шифрования содержит элементы, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.</span><span class="sxs-lookup"><span data-stu-id="92e6b-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
 [<span data-ttu-id="92e6b-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="92e6b-104">**\<configuration>**</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="92e6b-105"> **\<mscorlib>** </span><span class="sxs-lookup"><span data-stu-id="92e6b-105">**\<mscorlib>**</span></span>](mscorlib-element-for-cryptography-settings.md)  
  
 [<span data-ttu-id="92e6b-106"> **\<cryptographySettings>** </span><span class="sxs-lookup"><span data-stu-id="92e6b-106">**\<cryptographySettings>**</span></span>](cryptographysettings-element.md)  
  
 [<span data-ttu-id="92e6b-107"> **\<cryptoNameMapping>** </span><span class="sxs-lookup"><span data-stu-id="92e6b-107">**\<cryptoNameMapping>**</span></span>](cryptonamemapping-element.md)  
  
 [<span data-ttu-id="92e6b-108"> **\<cryptoClasses>** </span><span class="sxs-lookup"><span data-stu-id="92e6b-108">**\<cryptoClasses>**</span></span>](cryptoclasses-element.md)  
  
 [<span data-ttu-id="92e6b-109"> **\<cryptoClass>** </span><span class="sxs-lookup"><span data-stu-id="92e6b-109">**\<cryptoClass>**</span></span>](cryptoclass-element.md)  
  
 [<span data-ttu-id="92e6b-110"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="92e6b-110">**\<nameEntry>**</span></span>](nameentry-element.md)  
  
 [<span data-ttu-id="92e6b-111"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="92e6b-111">**\<oidMap>**</span></span>](oidmap-element.md)  
  
 [<span data-ttu-id="92e6b-112"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="92e6b-112">**\<oidEntry>**</span></span>](oidentry-element.md)  
  
|<span data-ttu-id="92e6b-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="92e6b-113">Element</span></span>|<span data-ttu-id="92e6b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="92e6b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92e6b-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="92e6b-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="92e6b-116">Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="92e6b-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="92e6b-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="92e6b-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="92e6b-118">Содержит криптографический класс, сопоставленный с понятным именем, указанным в элементе **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="92e6b-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="92e6b-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="92e6b-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="92e6b-120">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="92e6b-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="92e6b-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="92e6b-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="92e6b-122">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="92e6b-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="92e6b-123">Элемент **\<mscorlib>** для параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="92e6b-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="92e6b-124">Содержит элемент **\<cryptographySettings>** .</span><span class="sxs-lookup"><span data-stu-id="92e6b-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="92e6b-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="92e6b-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="92e6b-126">Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.</span><span class="sxs-lookup"><span data-stu-id="92e6b-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="92e6b-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="92e6b-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="92e6b-128">Сопоставляет идентификатор объекта (OID) ASN.1 с понятным именем.</span><span class="sxs-lookup"><span data-stu-id="92e6b-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="92e6b-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="92e6b-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="92e6b-130">Содержит сопоставления идентификатора объекта ASN.1 с классами.</span><span class="sxs-lookup"><span data-stu-id="92e6b-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92e6b-131">См. также</span><span class="sxs-lookup"><span data-stu-id="92e6b-131">See also</span></span>

- [<span data-ttu-id="92e6b-132">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="92e6b-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="92e6b-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="92e6b-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
