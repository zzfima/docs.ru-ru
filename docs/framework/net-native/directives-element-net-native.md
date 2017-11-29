---
title: "Элемент &lt;Directives&gt; (машинный код .NET)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a55048ea5b2889da82b10ac2a51865d945635143
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltdirectivesgt-element-net-native"></a><span data-ttu-id="a2f04-102">Элемент &lt;Directives&gt; (машинный код .NET)</span><span class="sxs-lookup"><span data-stu-id="a2f04-102">&lt;Directives&gt; Element (.NET Native)</span></span>
<span data-ttu-id="a2f04-103">Корневой элемент в любом файле директив среды выполнения для [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2f04-103">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="a2f04-104">**Директивы \< xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">**</span><span class="sxs-lookup"><span data-stu-id="a2f04-104">**\<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2f04-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2f04-105">Syntax</span></span>  
  
```xml  
      <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="a2f04-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a2f04-106">Attributes</span></span>  
  
|<span data-ttu-id="a2f04-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a2f04-107">Attribute</span></span>|<span data-ttu-id="a2f04-108">Описание</span><span class="sxs-lookup"><span data-stu-id="a2f04-108">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="a2f04-109">Пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="a2f04-109">The XML namespace.</span></span> <span data-ttu-id="a2f04-110">Всегда имеет значение **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span><span class="sxs-lookup"><span data-stu-id="a2f04-110">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="a2f04-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a2f04-111">Child elements</span></span>  
  
|<span data-ttu-id="a2f04-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="a2f04-112">Element</span></span>|<span data-ttu-id="a2f04-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a2f04-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2f04-114">\<Application></span><span class="sxs-lookup"><span data-stu-id="a2f04-114">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="a2f04-115">Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения.</span><span class="sxs-lookup"><span data-stu-id="a2f04-115">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="a2f04-116">\<Library></span><span class="sxs-lookup"><span data-stu-id="a2f04-116">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="a2f04-117">Определяет сборку, чьи дочерние типы и члены типов требуют метаданные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a2f04-117">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2f04-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="a2f04-118">Remarks</span></span>  
 <span data-ttu-id="a2f04-119">Каждый файл директив среды выполнения содержит только один элемент `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="a2f04-119">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="a2f04-120">Элемент `<Directives>` может содержать ноль или один элемент [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) и ноль, один или более элементов [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a2f04-120">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f04-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a2f04-121">See Also</span></span>  
 [<span data-ttu-id="a2f04-122">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="a2f04-122">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="a2f04-123">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a2f04-123">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
