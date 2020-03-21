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
ms.openlocfilehash: ed28ae4a52085cbfa781b4baf2ee1eafbeff6eb4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154833"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="b25e5-102">\<модуль> элемент (Настройки сети)</span><span class="sxs-lookup"><span data-stu-id="b25e5-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="b25e5-103">Добавляет в приложение новый модуль прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="b25e5-103">Adds a new proxy module to the application.</span></span>  

<span data-ttu-id="b25e5-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b25e5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b25e5-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b25e5-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="b25e5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<по умолчаниюПрокси>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b25e5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="b25e5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<модуль>**</span><span class="sxs-lookup"><span data-stu-id="b25e5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b25e5-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b25e5-108">Syntax</span></span>  
  
```xml  
<module
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b25e5-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b25e5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b25e5-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b25e5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b25e5-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b25e5-111">Attributes</span></span>  
  
|<span data-ttu-id="b25e5-112">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="b25e5-112">**Attribute**</span></span>|<span data-ttu-id="b25e5-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b25e5-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="b25e5-114">Полностью квалифицированное имя <xref:System.Type.FullName%2A> типа (указано свойством) <xref:System.Reflection.Assembly.FullName%2A> и название сборки (указанное свойством), разделенное запятой, которая реализует прокси.</span><span class="sxs-lookup"><span data-stu-id="b25e5-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b25e5-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b25e5-115">Child Elements</span></span>  
 <span data-ttu-id="b25e5-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="b25e5-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b25e5-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b25e5-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b25e5-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="b25e5-118">**Element**</span></span>|<span data-ttu-id="b25e5-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b25e5-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b25e5-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="b25e5-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="b25e5-121">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="b25e5-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b25e5-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="b25e5-122">Remarks</span></span>  
 <span data-ttu-id="b25e5-123">Элемент `module` регистрирует прокси-классы, <xref:System.Net.IWebProxy> реализующие интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b25e5-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="b25e5-124">После регистрации прокси-класса элемент `module` может использоваться для запроса данных через поддерживаемый прокси.</span><span class="sxs-lookup"><span data-stu-id="b25e5-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="b25e5-125">Значение множеству атрибута `type` должно быть классовым названием модуля и названием соответствующей библиотеки динамической ссылки (DLL).</span><span class="sxs-lookup"><span data-stu-id="b25e5-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b25e5-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="b25e5-126">Configuration Files</span></span>  
 <span data-ttu-id="b25e5-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b25e5-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b25e5-128">Пример</span><span class="sxs-lookup"><span data-stu-id="b25e5-128">Example</span></span>  
 <span data-ttu-id="b25e5-129">В следующем примере регистрируется пользовательский класс прокси.</span><span class="sxs-lookup"><span data-stu-id="b25e5-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b25e5-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b25e5-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="b25e5-131">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="b25e5-131">Network Settings Schema</span></span>](index.md)
