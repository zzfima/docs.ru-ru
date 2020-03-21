---
title: <Directives>Элемент (.NET Родной)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 49c1aaf005b80a6c1c1fa382eebc2cb0dbfa4be7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181045"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="c4fd0-102">\<Директивы> Элемент (.NET Родной)</span><span class="sxs-lookup"><span data-stu-id="c4fd0-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="c4fd0-103">Корневой элемент в каждом файле директив времени выполнения для .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c4fd0-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a><span data-ttu-id="c4fd0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4fd0-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="c4fd0-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c4fd0-105">Attributes</span></span>  
  
|<span data-ttu-id="c4fd0-106">attribute</span><span class="sxs-lookup"><span data-stu-id="c4fd0-106">Attribute</span></span>|<span data-ttu-id="c4fd0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c4fd0-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="c4fd0-108">Пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="c4fd0-108">The XML namespace.</span></span> <span data-ttu-id="c4fd0-109">Его ценность всегда **"http://schemas.microsoft.com/netfx/2013/01/metadata**.</span><span class="sxs-lookup"><span data-stu-id="c4fd0-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="c4fd0-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c4fd0-110">Child elements</span></span>  
  
|<span data-ttu-id="c4fd0-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="c4fd0-111">Element</span></span>|<span data-ttu-id="c4fd0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c4fd0-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4fd0-113">\<Применение></span><span class="sxs-lookup"><span data-stu-id="c4fd0-113">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="c4fd0-114">Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения.</span><span class="sxs-lookup"><span data-stu-id="c4fd0-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="c4fd0-115">\<Библиотечная></span><span class="sxs-lookup"><span data-stu-id="c4fd0-115">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="c4fd0-116">Определяет сборку, чьи дочерние типы и члены типов требуют метаданные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c4fd0-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4fd0-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="c4fd0-117">Remarks</span></span>  
 <span data-ttu-id="c4fd0-118">Каждый файл директив среды выполнения содержит только один элемент `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="c4fd0-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="c4fd0-119">Элемент `<Directives>` может содержать ноль или одно [ \<приложение>](application-element-net-native.md) элемент, а также ноль, один или несколько [ \<](library-element-net-native.md) элементов библиотеки>.</span><span class="sxs-lookup"><span data-stu-id="c4fd0-119">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4fd0-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c4fd0-120">See also</span></span>

- [<span data-ttu-id="c4fd0-121">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="c4fd0-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="c4fd0-122">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="c4fd0-122">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
