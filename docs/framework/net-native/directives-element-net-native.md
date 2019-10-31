---
title: Элемент <Directives> (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: abe2e7221e0afb984a6178b12fabc36ea24deb35
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128471"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="c0bc7-102">Директивы \<> элемента (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="c0bc7-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="c0bc7-103">Корневой элемент в каждом файле директив среды выполнения для .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c0bc7-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="c0bc7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0bc7-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="c0bc7-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c0bc7-105">Attributes</span></span>  
  
|<span data-ttu-id="c0bc7-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c0bc7-106">Attribute</span></span>|<span data-ttu-id="c0bc7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c0bc7-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="c0bc7-108">Пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="c0bc7-108">The XML namespace.</span></span> <span data-ttu-id="c0bc7-109">Его значение всегда равно **"http://schemas.microsoft.com/netfx/2013/01/metadata"** .</span><span class="sxs-lookup"><span data-stu-id="c0bc7-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="c0bc7-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c0bc7-110">Child elements</span></span>  
  
|<span data-ttu-id="c0bc7-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="c0bc7-111">Element</span></span>|<span data-ttu-id="c0bc7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c0bc7-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0bc7-113">\<Application></span><span class="sxs-lookup"><span data-stu-id="c0bc7-113">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="c0bc7-114">Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения.</span><span class="sxs-lookup"><span data-stu-id="c0bc7-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="c0bc7-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="c0bc7-115">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="c0bc7-116">Определяет сборку, чьи дочерние типы и члены типов требуют метаданные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c0bc7-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0bc7-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="c0bc7-117">Remarks</span></span>  
 <span data-ttu-id="c0bc7-118">Каждый файл директив среды выполнения содержит только один элемент `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="c0bc7-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="c0bc7-119">Элемент `<Directives>` может содержать ноль или один элемент [\<Application>](application-element-net-native.md) и ноль, один или более элементов [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="c0bc7-119">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0bc7-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c0bc7-120">See also</span></span>

- [<span data-ttu-id="c0bc7-121">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="c0bc7-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="c0bc7-122">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="c0bc7-122">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
