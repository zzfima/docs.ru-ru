---
title: Элемент <module> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: 15f4d10a70dc3c6abd32869f5b7b0006a799b4bf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698034"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="2ddd3-102">Элемент > @no__t 0module (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="2ddd3-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="2ddd3-103">Добавляет в приложение новый модуль прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="2ddd3-103">Adds a new proxy module to the application.</span></span>  
  
[<span data-ttu-id="2ddd3-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="2ddd3-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="2ddd3-105">&nbsp; @ no__t-1[ **@no__t -4system. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2ddd3-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="2ddd3-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2ddd3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="2ddd3-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<module >**</span><span class="sxs-lookup"><span data-stu-id="2ddd3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ddd3-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ddd3-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ddd3-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2ddd3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2ddd3-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2ddd3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ddd3-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2ddd3-111">Attributes</span></span>  
  
|<span data-ttu-id="2ddd3-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="2ddd3-112">**Attribute**</span></span>|<span data-ttu-id="2ddd3-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2ddd3-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="2ddd3-114">Полное имя типа (указанное свойством <xref:System.Type.FullName%2A>) и имя сборки (обозначенное свойством <xref:System.Reflection.Assembly.FullName%2A>), разделенные запятыми, которые реализуют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="2ddd3-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ddd3-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2ddd3-115">Child Elements</span></span>  
 <span data-ttu-id="2ddd3-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="2ddd3-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ddd3-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2ddd3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2ddd3-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2ddd3-118">**Element**</span></span>|<span data-ttu-id="2ddd3-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2ddd3-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2ddd3-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="2ddd3-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="2ddd3-121">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="2ddd3-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ddd3-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ddd3-122">Remarks</span></span>  
 <span data-ttu-id="2ddd3-123">Элемент `module` регистрирует прокси-классы, реализующие интерфейс <xref:System.Net.IWebProxy>.</span><span class="sxs-lookup"><span data-stu-id="2ddd3-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="2ddd3-124">После регистрации прокси-класса элемент `module` может использоваться для запроса данных через поддерживаемый прокси.</span><span class="sxs-lookup"><span data-stu-id="2ddd3-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="2ddd3-125">Значение атрибута `type` должно быть именем класса модуля и именем соответствующей библиотеки динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="2ddd3-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2ddd3-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="2ddd3-126">Configuration Files</span></span>  
 <span data-ttu-id="2ddd3-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2ddd3-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ddd3-128">Пример</span><span class="sxs-lookup"><span data-stu-id="2ddd3-128">Example</span></span>  
 <span data-ttu-id="2ddd3-129">В следующем примере регистрируется пользовательский прокси-класс.</span><span class="sxs-lookup"><span data-stu-id="2ddd3-129">The following example registers a custom proxy class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ddd3-130">См. также</span><span class="sxs-lookup"><span data-stu-id="2ddd3-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="2ddd3-131">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="2ddd3-131">Network Settings Schema</span></span>](index.md)
