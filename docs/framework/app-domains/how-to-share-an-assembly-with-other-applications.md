---
title: Практическое руководство. Совместное использование сборки с другими приложениями
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: b1ef195458dd2de95eeb5e25089339e55d9e3fbb
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972885"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a><span data-ttu-id="9b13f-102">Практическое руководство. Совместное использование сборки с другими приложениями</span><span class="sxs-lookup"><span data-stu-id="9b13f-102">How to: Share an assembly with other applications</span></span>
<span data-ttu-id="9b13f-103">Сборки могут быть закрытыми или общими. По умолчанию большинство простых программ состоят из закрытой сборки, так как она не предназначена для использования другими приложениями.</span><span class="sxs-lookup"><span data-stu-id="9b13f-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  

<span data-ttu-id="9b13f-104">Для совместного использования сборки с другими приложениями ее нужно поместить в [глобальный кэш сборок (GAC)](gac.md).</span><span class="sxs-lookup"><span data-stu-id="9b13f-104">In order to share an assembly with other applications, it must be placed in the [global assembly cache (GAC)](gac.md).</span></span>  
  
<span data-ttu-id="9b13f-105">Предоставление общего доступа к сборке:</span><span class="sxs-lookup"><span data-stu-id="9b13f-105">To share an assembly:</span></span>
  
1. <span data-ttu-id="9b13f-106">Создайте сборку.</span><span class="sxs-lookup"><span data-stu-id="9b13f-106">Create your assembly.</span></span> <span data-ttu-id="9b13f-107">Дополнительные сведения см. в разделе [Создание сборок](../../standard/assembly/create.md).</span><span class="sxs-lookup"><span data-stu-id="9b13f-107">For more information, see [Create assemblies](../../standard/assembly/create.md).</span></span>  
  
2. <span data-ttu-id="9b13f-108">Назначьте сборке строгое имя.</span><span class="sxs-lookup"><span data-stu-id="9b13f-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="9b13f-109">Дополнительные сведения см. в разделе [Практическое руководство. Подписание сборки со строгим именем](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="9b13f-109">For more information, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>  
  
3. <span data-ttu-id="9b13f-110">Назначьте сведения о версии для сборки.</span><span class="sxs-lookup"><span data-stu-id="9b13f-110">Assign version information to your assembly.</span></span> <span data-ttu-id="9b13f-111">Дополнительные сведения см. в разделе [Управление версиями сборок](../../standard/assembly/versioning.md).</span><span class="sxs-lookup"><span data-stu-id="9b13f-111">For more information, see [Assembly versioning](../../standard/assembly/versioning.md).</span></span>  
  
4. <span data-ttu-id="9b13f-112">Добавьте сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="9b13f-112">Add your assembly to the global assembly cache.</span></span> <span data-ttu-id="9b13f-113">Дополнительные сведения см. в разделе [Практическое руководство. Установка сборки в глобальный кэш сборок](install-assembly-into-gac.md).</span><span class="sxs-lookup"><span data-stu-id="9b13f-113">For more information, see [How to: Install an assembly into the global assembly cache](install-assembly-into-gac.md).</span></span>  
  
5. <span data-ttu-id="9b13f-114">Получите доступ к типам, содержащимся в сборке, из других приложений.</span><span class="sxs-lookup"><span data-stu-id="9b13f-114">Access the types contained in the assembly from other applications.</span></span> <span data-ttu-id="9b13f-115">Дополнительные сведения см. в разделе [Практическое руководство. Ссылка на сборку со строгим именем](../../standard/assembly/reference-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="9b13f-115">For more information, see [How to: Reference a strong-named assembly](../../standard/assembly/reference-strong-named.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b13f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9b13f-116">See also</span></span>

- [<span data-ttu-id="9b13f-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9b13f-117">C# programming guide</span></span>](../../../api/index.md)
- [<span data-ttu-id="9b13f-118">Основные понятия программирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b13f-118">Programming concepts (Visual Basic)</span></span>](../../../api/index.md)
- [<span data-ttu-id="9b13f-119">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="9b13f-119">Program with assemblies</span></span>](../../standard/assembly/program.md)
