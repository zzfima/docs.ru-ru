---
title: <Directives> Элемент (машинный код .NET)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cfc9dc5c8122f9b1b1696cedcd5d9a8ceead403
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61868592"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="a64fe-102">\<Директивы > элемент (машинный код .NET)</span><span class="sxs-lookup"><span data-stu-id="a64fe-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="a64fe-103">Корневой элемент в любом файле директив среды выполнения для машинного кода .NET.</span><span class="sxs-lookup"><span data-stu-id="a64fe-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="a64fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a64fe-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="a64fe-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a64fe-105">Attributes</span></span>  
  
|<span data-ttu-id="a64fe-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a64fe-106">Attribute</span></span>|<span data-ttu-id="a64fe-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a64fe-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="a64fe-108">Пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="a64fe-108">The XML namespace.</span></span> <span data-ttu-id="a64fe-109">Всегда имеет значение **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span><span class="sxs-lookup"><span data-stu-id="a64fe-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="a64fe-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a64fe-110">Child elements</span></span>  
  
|<span data-ttu-id="a64fe-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="a64fe-111">Element</span></span>|<span data-ttu-id="a64fe-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a64fe-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a64fe-113">\<Application></span><span class="sxs-lookup"><span data-stu-id="a64fe-113">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="a64fe-114">Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения.</span><span class="sxs-lookup"><span data-stu-id="a64fe-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="a64fe-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="a64fe-115">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="a64fe-116">Определяет сборку, чьи дочерние типы и члены типов требуют метаданные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a64fe-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a64fe-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="a64fe-117">Remarks</span></span>  
 <span data-ttu-id="a64fe-118">Каждый файл директив среды выполнения содержит только один элемент `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="a64fe-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="a64fe-119">Элемент `<Directives>` может содержать ноль или один элемент [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) и ноль, один или более элементов [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a64fe-119">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a64fe-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a64fe-120">See also</span></span>

- [<span data-ttu-id="a64fe-121">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="a64fe-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="a64fe-122">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a64fe-122">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
