---
title: '&lt;enforceFIPSPolicy&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9040bf2548964cf6df5f4fd87ee9f6d979c7df1e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltenforcefipspolicygt-element"></a><span data-ttu-id="beab3-102">&lt;enforceFIPSPolicy&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="beab3-102">&lt;enforceFIPSPolicy&gt; Element</span></span>
<span data-ttu-id="beab3-103">Указывает, нужно ли принудительно обеспечивать соблюдение требования конфигурации компьютера о том, что криптографические алгоритмы должны соответствовать стандартам FIPS.</span><span class="sxs-lookup"><span data-stu-id="beab3-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="beab3-104">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="beab3-104">\<configuration> Element</span></span>  
<span data-ttu-id="beab3-105">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="beab3-105">\<runtime> Element</span></span>  
<span data-ttu-id="beab3-106">\<enforceFIPSPolicy > элемент</span><span class="sxs-lookup"><span data-stu-id="beab3-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beab3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="beab3-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="beab3-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="beab3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="beab3-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="beab3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="beab3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="beab3-110">Attributes</span></span>  
  
|<span data-ttu-id="beab3-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="beab3-111">Attribute</span></span>|<span data-ttu-id="beab3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="beab3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="beab3-113">enabled</span><span class="sxs-lookup"><span data-stu-id="beab3-113">enabled</span></span>|<span data-ttu-id="beab3-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="beab3-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="beab3-115">Указывает, следует ли включить применение требования конфигурации компьютера, алгоритмов шифрования должна быть совместима с FIPS.</span><span class="sxs-lookup"><span data-stu-id="beab3-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="beab3-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="beab3-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="beab3-117">Значение</span><span class="sxs-lookup"><span data-stu-id="beab3-117">Value</span></span>|<span data-ttu-id="beab3-118">Описание</span><span class="sxs-lookup"><span data-stu-id="beab3-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="beab3-119">Если компьютер настроен требовать быть FIPS-совместимые алгоритмы шифрования, это требование применяется.</span><span class="sxs-lookup"><span data-stu-id="beab3-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="beab3-120">Если класс реализует алгоритм, который не соответствует стандарту FIPS, конструкторы или `Create` методы для этого класса вызывать исключения, когда они запускаются на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="beab3-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="beab3-121">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="beab3-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="beab3-122">Алгоритмы шифрования, которые используются в приложении не требуются для соответствия FIPS, вне зависимости от конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="beab3-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="beab3-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="beab3-123">Child Elements</span></span>  
 <span data-ttu-id="beab3-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="beab3-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="beab3-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="beab3-125">Parent Elements</span></span>  
  
|<span data-ttu-id="beab3-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="beab3-126">Element</span></span>|<span data-ttu-id="beab3-127">Описание</span><span class="sxs-lookup"><span data-stu-id="beab3-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="beab3-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="beab3-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="beab3-129">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="beab3-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="beab3-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="beab3-130">Remarks</span></span>  
 <span data-ttu-id="beab3-131">Начиная с .NET Framework 2.0, создания классов, реализующих алгоритмы шифрования управляется конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="beab3-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="beab3-132">Если компьютер настроен требовать соответствие стандарту FIPS алгоритмы и класса, реализующего алгоритм, который не соответствует стандарту FIPS, любая попытка создать экземпляр этого класса создает исключение.</span><span class="sxs-lookup"><span data-stu-id="beab3-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="beab3-133">Конструкторы вызывать <xref:System.InvalidOperationException> исключение, и `Create` методы создают исключение <xref:System.Reflection.TargetInvocationException> исключение внутренний <xref:System.InvalidOperationException> исключение.</span><span class="sxs-lookup"><span data-stu-id="beab3-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="beab3-134">Если приложение выполняется на компьютерах, на которых конфигурации требуют соответствия стандарту FIPS, и приложение использует алгоритм, который не соответствует стандарту FIPS, можно использовать этот элемент в файле конфигурации для предотвращения выполнения (CLR) из обеспечение соответствия FIPS.</span><span class="sxs-lookup"><span data-stu-id="beab3-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="beab3-135">Этот элемент был введен в [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="beab3-135">This element was introduced in the [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="beab3-136">Пример</span><span class="sxs-lookup"><span data-stu-id="beab3-136">Example</span></span>  
 <span data-ttu-id="beab3-137">Приведенный ниже показано, как предотвратить обеспечение соответствия FIPS в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="beab3-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="beab3-138">См. также</span><span class="sxs-lookup"><span data-stu-id="beab3-138">See Also</span></span>  
 [<span data-ttu-id="beab3-139">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="beab3-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="beab3-140">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="beab3-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="beab3-141">Модель криптографии</span><span class="sxs-lookup"><span data-stu-id="beab3-141">Cryptography Model</span></span>](../../../../../docs/standard/security/cryptography-model.md)
