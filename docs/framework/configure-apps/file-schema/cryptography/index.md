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
ms.openlocfilehash: c632a15552c8ba5743aac1309098b7d7ef949bbd
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088003"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="07c2a-102">Схема параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="07c2a-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="07c2a-103">Схема параметров шифрования содержит элементы, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.</span><span class="sxs-lookup"><span data-stu-id="07c2a-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
<span data-ttu-id="07c2a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="07c2a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="07c2a-105">&nbsp;&nbsp;[ **\<> mscorlib**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="07c2a-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="07c2a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптографисеттингс >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="07c2a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="07c2a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптонамемаппинг >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="07c2a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>\
<span data-ttu-id="07c2a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптоклассес >** ](cryptoclasses-element.md)</span><span class="sxs-lookup"><span data-stu-id="07c2a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>\
<span data-ttu-id="07c2a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoClass >** ](cryptoclass-element.md)</span><span class="sxs-lookup"><span data-stu-id="07c2a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)</span></span>\
<span data-ttu-id="07c2a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<элементе nameentry >** ](nameentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="07c2a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)</span></span>\
<span data-ttu-id="07c2a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<оидмап >** ](oidmap-element.md)</span><span class="sxs-lookup"><span data-stu-id="07c2a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>\
<span data-ttu-id="07c2a-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<оидентри >** ](oidentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="07c2a-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)</span></span>

|<span data-ttu-id="07c2a-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="07c2a-113">Element</span></span>|<span data-ttu-id="07c2a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="07c2a-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07c2a-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="07c2a-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="07c2a-116">Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="07c2a-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="07c2a-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="07c2a-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="07c2a-118">Содержит криптографический класс, сопоставленный с понятным именем, указанным в элементе **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="07c2a-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="07c2a-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="07c2a-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="07c2a-120">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="07c2a-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="07c2a-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="07c2a-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="07c2a-122">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="07c2a-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="07c2a-123">Элемент **\<mscorlib>** для параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="07c2a-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="07c2a-124">Содержит элемент **\<cryptographySettings>** .</span><span class="sxs-lookup"><span data-stu-id="07c2a-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="07c2a-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="07c2a-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="07c2a-126">Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.</span><span class="sxs-lookup"><span data-stu-id="07c2a-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="07c2a-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="07c2a-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="07c2a-128">Сопоставляет идентификатор объекта (OID) ASN.1 с понятным именем.</span><span class="sxs-lookup"><span data-stu-id="07c2a-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="07c2a-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="07c2a-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="07c2a-130">Содержит сопоставления идентификатора объекта ASN.1 с классами.</span><span class="sxs-lookup"><span data-stu-id="07c2a-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07c2a-131">См. также</span><span class="sxs-lookup"><span data-stu-id="07c2a-131">See also</span></span>

- [<span data-ttu-id="07c2a-132">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="07c2a-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="07c2a-133">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="07c2a-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
