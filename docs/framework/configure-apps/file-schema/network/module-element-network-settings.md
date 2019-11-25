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
ms.openlocfilehash: 78f6418160b80096214c6e37268a5a90498d6d4d
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089238"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="9fb57-102">Элемент > модуля \<(параметры сети)</span><span class="sxs-lookup"><span data-stu-id="9fb57-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="9fb57-103">Добавляет в приложение новый модуль прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="9fb57-103">Adds a new proxy module to the application.</span></span>  

<span data-ttu-id="9fb57-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9fb57-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9fb57-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9fb57-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="9fb57-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9fb57-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="9fb57-107">&nbsp;&nbsp;&nbsp;&nbsp; **&nbsp;&nbsp;\<** ></span><span class="sxs-lookup"><span data-stu-id="9fb57-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9fb57-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fb57-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fb57-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9fb57-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9fb57-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9fb57-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fb57-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9fb57-111">Attributes</span></span>  
  
|<span data-ttu-id="9fb57-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="9fb57-112">**Attribute**</span></span>|<span data-ttu-id="9fb57-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9fb57-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="9fb57-114">Полное имя типа (обозначенное свойством <xref:System.Type.FullName%2A>) и имя сборки (обозначенное свойством <xref:System.Reflection.Assembly.FullName%2A>), разделенные запятыми, которые реализуют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="9fb57-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fb57-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9fb57-115">Child Elements</span></span>  
 <span data-ttu-id="9fb57-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9fb57-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9fb57-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9fb57-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9fb57-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="9fb57-118">**Element**</span></span>|<span data-ttu-id="9fb57-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9fb57-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9fb57-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="9fb57-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="9fb57-121">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="9fb57-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fb57-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="9fb57-122">Remarks</span></span>  
 <span data-ttu-id="9fb57-123">Элемент `module` регистрирует прокси-классы, реализующие интерфейс <xref:System.Net.IWebProxy>.</span><span class="sxs-lookup"><span data-stu-id="9fb57-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="9fb57-124">После регистрации прокси-класса элемент `module` может использоваться для запроса данных через поддерживаемый прокси.</span><span class="sxs-lookup"><span data-stu-id="9fb57-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="9fb57-125">Значение атрибута `type` должно быть именем класса модуля и именем соответствующей библиотеки динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="9fb57-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9fb57-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="9fb57-126">Configuration Files</span></span>  
 <span data-ttu-id="9fb57-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="9fb57-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fb57-128">Пример</span><span class="sxs-lookup"><span data-stu-id="9fb57-128">Example</span></span>  
 <span data-ttu-id="9fb57-129">В следующем примере регистрируется пользовательский прокси-класс.</span><span class="sxs-lookup"><span data-stu-id="9fb57-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9fb57-130">См. также</span><span class="sxs-lookup"><span data-stu-id="9fb57-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="9fb57-131">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="9fb57-131">Network Settings Schema</span></span>](index.md)
