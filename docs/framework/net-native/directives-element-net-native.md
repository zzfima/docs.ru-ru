---
title: <Directives>Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9ec9a09e2fc03adbfcff0d7e69489e37da6e4a5
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049881"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="25ad3-102">\<Директивы > элемент (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="25ad3-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="25ad3-103">Корневой элемент в каждом файле директив среды выполнения для .NET Native.</span><span class="sxs-lookup"><span data-stu-id="25ad3-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="25ad3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25ad3-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="25ad3-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="25ad3-105">Attributes</span></span>  
  
|<span data-ttu-id="25ad3-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="25ad3-106">Attribute</span></span>|<span data-ttu-id="25ad3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="25ad3-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="25ad3-108">Пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="25ad3-108">The XML namespace.</span></span> <span data-ttu-id="25ad3-109">Его значение всегда равно **"http://schemas.microsoft.com/netfx/2013/01/metadata"** .</span><span class="sxs-lookup"><span data-stu-id="25ad3-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="25ad3-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="25ad3-110">Child elements</span></span>  
  
|<span data-ttu-id="25ad3-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="25ad3-111">Element</span></span>|<span data-ttu-id="25ad3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="25ad3-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25ad3-113">\<Application></span><span class="sxs-lookup"><span data-stu-id="25ad3-113">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="25ad3-114">Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения.</span><span class="sxs-lookup"><span data-stu-id="25ad3-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="25ad3-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="25ad3-115">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="25ad3-116">Определяет сборку, чьи дочерние типы и члены типов требуют метаданные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="25ad3-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25ad3-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="25ad3-117">Remarks</span></span>  
 <span data-ttu-id="25ad3-118">Каждый файл директив среды выполнения содержит только один элемент `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="25ad3-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="25ad3-119">Элемент `<Directives>` может содержать ноль или один элемент [\<Application>](application-element-net-native.md) и ноль, один или более элементов [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="25ad3-119">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ad3-120">См. также</span><span class="sxs-lookup"><span data-stu-id="25ad3-120">See also</span></span>

- [<span data-ttu-id="25ad3-121">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="25ad3-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="25ad3-122">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="25ad3-122">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
