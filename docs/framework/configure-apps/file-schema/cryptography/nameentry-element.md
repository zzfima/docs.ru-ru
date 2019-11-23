---
title: Элемент <nameEntry>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: a339638587f8b544bbc1b0073553f6232ce09694
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699777"
---
# <a name="nameentry-element"></a><span data-ttu-id="76333-102">\<элементе nameentry > элемент</span><span class="sxs-lookup"><span data-stu-id="76333-102">\<nameEntry> Element</span></span>
<span data-ttu-id="76333-103">Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.</span><span class="sxs-lookup"><span data-stu-id="76333-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
[<span data-ttu-id="76333-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="76333-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="76333-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="76333-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="76333-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптографисеттингс >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="76333-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="76333-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптонамемаппинг >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="76333-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="76333-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<элементе nameentry >**</span><span class="sxs-lookup"><span data-stu-id="76333-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameEntry>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76333-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76333-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76333-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="76333-110">Attributes and Elements</span></span>  
 <span data-ttu-id="76333-111">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="76333-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76333-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="76333-112">Attributes</span></span>  
  
|<span data-ttu-id="76333-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="76333-113">Attribute</span></span>|<span data-ttu-id="76333-114">Описание</span><span class="sxs-lookup"><span data-stu-id="76333-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76333-115">**name**</span><span class="sxs-lookup"><span data-stu-id="76333-115">**name**</span></span>|<span data-ttu-id="76333-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="76333-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="76333-117">Указывает понятное имя алгоритма, реализуемого криптографическим классом.</span><span class="sxs-lookup"><span data-stu-id="76333-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="76333-118">**класс**</span><span class="sxs-lookup"><span data-stu-id="76333-118">**class**</span></span>|<span data-ttu-id="76333-119">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="76333-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="76333-120">Задает значение для атрибута **Name** в элементе [\<cryptoClass >](cryptoclass-element.md) .</span><span class="sxs-lookup"><span data-stu-id="76333-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76333-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="76333-121">Child Elements</span></span>  
 <span data-ttu-id="76333-122">Нет</span><span class="sxs-lookup"><span data-stu-id="76333-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76333-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="76333-123">Parent Elements</span></span>  
  
|<span data-ttu-id="76333-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="76333-124">Element</span></span>|<span data-ttu-id="76333-125">Описание</span><span class="sxs-lookup"><span data-stu-id="76333-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="76333-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="76333-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="76333-127">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="76333-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76333-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="76333-128">Remarks</span></span>  
 <span data-ttu-id="76333-129">Атрибут **Name** может быть именем одного из абстрактных классов, найденных в пространстве имен <xref:System.Security.Cryptography>.</span><span class="sxs-lookup"><span data-stu-id="76333-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="76333-130">При вызове метода **CREATE** для абстрактного криптографического класса имя абстрактного класса передается в метод <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>.</span><span class="sxs-lookup"><span data-stu-id="76333-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="76333-131">**CreateFromName** возвращает экземпляр типа, указанного атрибутом **класса** .</span><span class="sxs-lookup"><span data-stu-id="76333-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="76333-132">Если атрибут **Name** имеет короткое имя, например RSA, это имя можно использовать при вызове метода **CreateFromName** .</span><span class="sxs-lookup"><span data-stu-id="76333-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76333-133">Пример</span><span class="sxs-lookup"><span data-stu-id="76333-133">Example</span></span>  
 <span data-ttu-id="76333-134">В следующем примере показано, как использовать элемент **\<элементе nameentry >** для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="76333-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="76333-135">Затем можно передать строку "RSA" в метод <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> и использовать метод <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> для возврата объекта `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="76333-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="76333-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="76333-136">See also</span></span>

- [<span data-ttu-id="76333-137">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="76333-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="76333-138">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="76333-138">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="76333-139">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="76333-139">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="76333-140">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="76333-140">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
