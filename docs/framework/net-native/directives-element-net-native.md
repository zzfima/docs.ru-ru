---
title: Элемент &lt;Directives&gt; (машинный код .NET)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd571255f924c9f3878c00a2bc01397d63e6d777
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394450"
---
# <a name="ltdirectivesgt-element-net-native"></a><span data-ttu-id="cef27-102">Элемент &lt;Directives&gt; (машинный код .NET)</span><span class="sxs-lookup"><span data-stu-id="cef27-102">&lt;Directives&gt; Element (.NET Native)</span></span>
<span data-ttu-id="cef27-103">Корневой элемент в любом файле директив среды выполнения для [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cef27-103">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="cef27-104">**\<Директивы xmlns =»http://schemas.microsoft.com/netfx/2013/01/metadata«>**</span><span class="sxs-lookup"><span data-stu-id="cef27-104">**\<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cef27-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cef27-105">Syntax</span></span>  
  
```xml  
      <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="cef27-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cef27-106">Attributes</span></span>  
  
|<span data-ttu-id="cef27-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cef27-107">Attribute</span></span>|<span data-ttu-id="cef27-108">Описание</span><span class="sxs-lookup"><span data-stu-id="cef27-108">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="cef27-109">Пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="cef27-109">The XML namespace.</span></span> <span data-ttu-id="cef27-110">Всегда имеет значение **»http://schemas.microsoft.com/netfx/2013/01/metadata»**.</span><span class="sxs-lookup"><span data-stu-id="cef27-110">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="cef27-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cef27-111">Child elements</span></span>  
  
|<span data-ttu-id="cef27-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="cef27-112">Element</span></span>|<span data-ttu-id="cef27-113">Описание</span><span class="sxs-lookup"><span data-stu-id="cef27-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cef27-114">\<Application></span><span class="sxs-lookup"><span data-stu-id="cef27-114">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="cef27-115">Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения.</span><span class="sxs-lookup"><span data-stu-id="cef27-115">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="cef27-116">\<Library></span><span class="sxs-lookup"><span data-stu-id="cef27-116">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="cef27-117">Определяет сборку, чьи дочерние типы и члены типов требуют метаданные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cef27-117">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cef27-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="cef27-118">Remarks</span></span>  
 <span data-ttu-id="cef27-119">Каждый файл директив среды выполнения содержит только один элемент `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="cef27-119">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="cef27-120">Элемент `<Directives>` может содержать ноль или один элемент [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) и ноль, один или более элементов [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="cef27-120">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cef27-121">См. также</span><span class="sxs-lookup"><span data-stu-id="cef27-121">See Also</span></span>  
 [<span data-ttu-id="cef27-122">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="cef27-122">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="cef27-123">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="cef27-123">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
