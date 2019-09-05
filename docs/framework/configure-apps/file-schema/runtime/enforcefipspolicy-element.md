---
title: Элемент <enforceFIPSPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f90abf9f6c2bc0aed2cf01558b2c0cca4e967e81
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252636"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="370d7-102">\<Элемент > Енфорцефипсполици</span><span class="sxs-lookup"><span data-stu-id="370d7-102">\<enforceFIPSPolicy> Element</span></span>
<span data-ttu-id="370d7-103">Указывает, нужно ли принудительно обеспечивать соблюдение требования конфигурации компьютера о том, что криптографические алгоритмы должны соответствовать стандартам FIPS.</span><span class="sxs-lookup"><span data-stu-id="370d7-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
<span data-ttu-id="370d7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="370d7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="370d7-105">&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="370d7-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="370d7-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<enforceFIPSPolicy>**</span><span class="sxs-lookup"><span data-stu-id="370d7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<enforceFIPSPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="370d7-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="370d7-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="370d7-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="370d7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="370d7-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="370d7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="370d7-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="370d7-110">Attributes</span></span>  
  
|<span data-ttu-id="370d7-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="370d7-111">Attribute</span></span>|<span data-ttu-id="370d7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="370d7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="370d7-113">enabled</span><span class="sxs-lookup"><span data-stu-id="370d7-113">enabled</span></span>|<span data-ttu-id="370d7-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="370d7-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="370d7-115">Указывает, следует ли включить принудительное применение конфигурации компьютера, чтобы алгоритмы шифрования должны соответствовать стандарту FIPS.</span><span class="sxs-lookup"><span data-stu-id="370d7-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="370d7-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="370d7-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="370d7-117">Значение</span><span class="sxs-lookup"><span data-stu-id="370d7-117">Value</span></span>|<span data-ttu-id="370d7-118">Описание</span><span class="sxs-lookup"><span data-stu-id="370d7-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="370d7-119">Если компьютер настроен для использования алгоритмов шифрования, совместимых с FIPS, это требование применяется принудительно.</span><span class="sxs-lookup"><span data-stu-id="370d7-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="370d7-120">Если класс реализует алгоритм, не соответствующий стандарту FIPS, конструкторы или `Create` методы этого класса создают исключения при запуске на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="370d7-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="370d7-121">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="370d7-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="370d7-122">Алгоритмы шифрования, используемые приложением, не должны соответствовать требованиям FIPS, независимо от конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="370d7-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="370d7-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="370d7-123">Child Elements</span></span>  
 <span data-ttu-id="370d7-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="370d7-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="370d7-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="370d7-125">Parent Elements</span></span>  
  
|<span data-ttu-id="370d7-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="370d7-126">Element</span></span>|<span data-ttu-id="370d7-127">Описание</span><span class="sxs-lookup"><span data-stu-id="370d7-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="370d7-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="370d7-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="370d7-129">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="370d7-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="370d7-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="370d7-130">Remarks</span></span>  
 <span data-ttu-id="370d7-131">Начиная с .NET Framework 2,0, создание классов, реализующих алгоритмы шифрования, управляется конфигурацией компьютера.</span><span class="sxs-lookup"><span data-stu-id="370d7-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="370d7-132">Если компьютер настроен на требование соответствия алгоритмам FIPS, а класс реализует алгоритм, который не соответствует стандарту FIPS, любая попытка создать экземпляр этого класса вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="370d7-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="370d7-133">Конструкторы создают <xref:System.InvalidOperationException> исключение, а `Create` методы вызывают <xref:System.Reflection.TargetInvocationException> исключение с внутренним <xref:System.InvalidOperationException> исключением.</span><span class="sxs-lookup"><span data-stu-id="370d7-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="370d7-134">Если приложение выполняется на компьютерах, конфигурация которых требует соответствия стандарту FIPS, а приложение использует алгоритм, не соответствующий стандарту FIPS, этот элемент можно использовать в файле конфигурации, чтобы предотвратить выполнение средой CLR обеспечение соответствия FIPS.</span><span class="sxs-lookup"><span data-stu-id="370d7-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="370d7-135">Этот элемент появился в .NET Framework 2,0 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="370d7-135">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="370d7-136">Пример</span><span class="sxs-lookup"><span data-stu-id="370d7-136">Example</span></span>  
 <span data-ttu-id="370d7-137">В следующем примере показано, как запретить среде CLR принудительно применять соответствие FIPS.</span><span class="sxs-lookup"><span data-stu-id="370d7-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="370d7-138">См. также</span><span class="sxs-lookup"><span data-stu-id="370d7-138">See also</span></span>

- [<span data-ttu-id="370d7-139">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="370d7-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="370d7-140">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="370d7-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="370d7-141">Модель криптографии</span><span class="sxs-lookup"><span data-stu-id="370d7-141">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)
