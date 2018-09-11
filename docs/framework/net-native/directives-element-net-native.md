---
title: Элемент &lt;Directives&gt; (машинный код .NET)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8921d2841f9a7b4228ae3b8735d7047453f71bcb
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44267145"
---
# <a name="ltdirectivesgt-element-net-native"></a><span data-ttu-id="88dd4-102">Элемент &lt;Directives&gt; (машинный код .NET)</span><span class="sxs-lookup"><span data-stu-id="88dd4-102">&lt;Directives&gt; Element (.NET Native)</span></span>
<span data-ttu-id="88dd4-103">Корневой элемент в любом файле директив среды выполнения для машинного кода .NET.</span><span class="sxs-lookup"><span data-stu-id="88dd4-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="88dd4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88dd4-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="88dd4-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="88dd4-105">Attributes</span></span>  
  
|<span data-ttu-id="88dd4-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="88dd4-106">Attribute</span></span>|<span data-ttu-id="88dd4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="88dd4-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="88dd4-108">Пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="88dd4-108">The XML namespace.</span></span> <span data-ttu-id="88dd4-109">Всегда имеет значение **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span><span class="sxs-lookup"><span data-stu-id="88dd4-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="88dd4-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="88dd4-110">Child elements</span></span>  
  
|<span data-ttu-id="88dd4-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="88dd4-111">Element</span></span>|<span data-ttu-id="88dd4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="88dd4-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88dd4-113">\<Application></span><span class="sxs-lookup"><span data-stu-id="88dd4-113">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="88dd4-114">Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения.</span><span class="sxs-lookup"><span data-stu-id="88dd4-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="88dd4-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="88dd4-115">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="88dd4-116">Определяет сборку, чьи дочерние типы и члены типов требуют метаданные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="88dd4-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88dd4-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="88dd4-117">Remarks</span></span>  
 <span data-ttu-id="88dd4-118">Каждый файл директив среды выполнения содержит только один элемент `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="88dd4-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="88dd4-119">Элемент `<Directives>` может содержать ноль или один элемент [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) и ноль, один или более элементов [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="88dd4-119">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88dd4-120">См. также</span><span class="sxs-lookup"><span data-stu-id="88dd4-120">See Also</span></span>  
 [<span data-ttu-id="88dd4-121">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="88dd4-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="88dd4-122">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="88dd4-122">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
