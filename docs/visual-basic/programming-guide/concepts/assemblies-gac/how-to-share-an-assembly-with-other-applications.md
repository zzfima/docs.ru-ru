---
title: Как выполнить Совместное использование сборки с другими приложениями (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
ms.openlocfilehash: d0e1dafc700b55a63342331b3280337d2c93cbd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631832"
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="97373-102">Как выполнить Совместное использование сборки с другими приложениями (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97373-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="97373-103">Сборки могут быть закрытыми или общими. По умолчанию большинство простых программ состоят из закрытой сборки, так как она не предназначена для использования другими приложениями.</span><span class="sxs-lookup"><span data-stu-id="97373-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="97373-104">Для совместного использования сборки с другими приложениями ее необходимо поместить в [глобальный кэш сборок](../../../../framework/app-domains/gac.md) (GAC).</span><span class="sxs-lookup"><span data-stu-id="97373-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="97373-105">Предоставление общего доступа к сборке</span><span class="sxs-lookup"><span data-stu-id="97373-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="97373-106">Создайте сборку.</span><span class="sxs-lookup"><span data-stu-id="97373-106">Create your assembly.</span></span> <span data-ttu-id="97373-107">Дополнительные сведения см. в разделе [Создание сборок](../../../../framework/app-domains/create-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="97373-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="97373-108">Назначьте сборке строгое имя.</span><span class="sxs-lookup"><span data-stu-id="97373-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="97373-109">Дополнительные сведения см. в разделе [Как Подписание сборки строгим именем](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="97373-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="97373-110">Назначьте сведения о версии для сборки.</span><span class="sxs-lookup"><span data-stu-id="97373-110">Assign version information to your assembly.</span></span> <span data-ttu-id="97373-111">Дополнительные сведения см. в разделе [Версии сборок](../../../../framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="97373-111">For more information, see [Assembly Versioning](../../../../framework/app-domains/assembly-versioning.md).</span></span>  
  
4.  <span data-ttu-id="97373-112">Добавьте сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="97373-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="97373-113">Дополнительные сведения см. в разделе [Как Установка сборки в глобальный кэш сборок](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="97373-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="97373-114">Получите доступ к типам, содержащимся в сборке, из других приложений.</span><span class="sxs-lookup"><span data-stu-id="97373-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="97373-115">Дополнительные сведения см. в разделе [Как Ссылки на сборку со строгим именем](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="97373-115">For more information, see [How to: Reference a Strong-Named Assembly](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97373-116">См. также</span><span class="sxs-lookup"><span data-stu-id="97373-116">See also</span></span>

- [<span data-ttu-id="97373-117">Основные понятия программирования</span><span class="sxs-lookup"><span data-stu-id="97373-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="97373-118">Сборки и глобальный кэш сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97373-118">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [<span data-ttu-id="97373-119">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="97373-119">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
