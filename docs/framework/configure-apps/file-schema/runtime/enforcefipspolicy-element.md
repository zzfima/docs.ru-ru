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
ms.openlocfilehash: 0bffe72a4bcadb4a36a9ac54263d55e242ffc4d4
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612014"
---
# <a name="ltenforcefipspolicygt-element"></a><span data-ttu-id="ebdf0-102">&lt;enforceFIPSPolicy&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="ebdf0-102">&lt;enforceFIPSPolicy&gt; Element</span></span>
<span data-ttu-id="ebdf0-103">Указывает, нужно ли принудительно обеспечивать соблюдение требования конфигурации компьютера о том, что криптографические алгоритмы должны соответствовать стандартам FIPS.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="ebdf0-104">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="ebdf0-104">\<configuration> Element</span></span>  
<span data-ttu-id="ebdf0-105">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="ebdf0-105">\<runtime> Element</span></span>  
<span data-ttu-id="ebdf0-106">\<enforceFIPSPolicy > элемент</span><span class="sxs-lookup"><span data-stu-id="ebdf0-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebdf0-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebdf0-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ebdf0-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ebdf0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ebdf0-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ebdf0-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ebdf0-110">Attributes</span></span>  
  
|<span data-ttu-id="ebdf0-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ebdf0-111">Attribute</span></span>|<span data-ttu-id="ebdf0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ebdf0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ebdf0-113">enabled</span><span class="sxs-lookup"><span data-stu-id="ebdf0-113">enabled</span></span>|<span data-ttu-id="ebdf0-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="ebdf0-115">Указывает, следует ли включить применение требования конфигурации компьютера, что необходимо соответствие стандарту FIPS алгоритмы шифрования.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ebdf0-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="ebdf0-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="ebdf0-117">Значение</span><span class="sxs-lookup"><span data-stu-id="ebdf0-117">Value</span></span>|<span data-ttu-id="ebdf0-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="ebdf0-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="ebdf0-119">Если компьютер настроен требовать соответствовала стандарту FIPS алгоритмы шифрования, это требование применяется принудительно.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="ebdf0-120">Если класс реализует алгоритм, который не соответствует стандарту FIPS, конструкторы или `Create` методы для этого класса исключения, когда они запускаются на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="ebdf0-121">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="ebdf0-122">Алгоритмы шифрования, которые используются приложением не требуется соответствие стандарту FIPS, независимо от конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ebdf0-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ebdf0-123">Child Elements</span></span>  
 <span data-ttu-id="ebdf0-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ebdf0-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ebdf0-125">Parent Elements</span></span>  
  
|<span data-ttu-id="ebdf0-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="ebdf0-126">Element</span></span>|<span data-ttu-id="ebdf0-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="ebdf0-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ebdf0-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ebdf0-129">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebdf0-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="ebdf0-130">Remarks</span></span>  
 <span data-ttu-id="ebdf0-131">Начиная с .NET Framework 2.0, создания классов, которые реализуют алгоритмы шифрования управляет конфигурацией компьютера.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="ebdf0-132">Если компьютер настроен требовать соответствие стандарту FIPS алгоритмы, а класс реализует алгоритм, который не соответствует стандарту FIPS, любая попытка создать экземпляр этого класса создает исключение.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="ebdf0-133">Конструкторы вызывать <xref:System.InvalidOperationException> исключение, и `Create` методы вызывают исключение <xref:System.Reflection.TargetInvocationException> исключение с внутренним <xref:System.InvalidOperationException> исключение.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="ebdf0-134">Если ваше приложение выполняется на компьютерах, если их конфигурация требуют соответствия стандарту FIPS, а приложение использует алгоритм, который не соответствует стандарту FIPS, можно использовать этот элемент в файле конфигурации для предотвращения среда CLR (CLR) из обеспечение соответствия FIPS.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="ebdf0-135">Этот элемент был введен в [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ebdf0-135">This element was introduced in the [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebdf0-136">Пример</span><span class="sxs-lookup"><span data-stu-id="ebdf0-136">Example</span></span>  
 <span data-ttu-id="ebdf0-137">В следующем примере показано, как помешать среде CLR обеспечивать соответствие требованиям FIPS применения.</span><span class="sxs-lookup"><span data-stu-id="ebdf0-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ebdf0-138">См. также</span><span class="sxs-lookup"><span data-stu-id="ebdf0-138">See Also</span></span>  
- [<span data-ttu-id="ebdf0-139">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ebdf0-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="ebdf0-140">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="ebdf0-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="ebdf0-141">Модель криптографии</span><span class="sxs-lookup"><span data-stu-id="ebdf0-141">Cryptography Model</span></span>](../../../../../docs/standard/security/cryptography-model.md)
