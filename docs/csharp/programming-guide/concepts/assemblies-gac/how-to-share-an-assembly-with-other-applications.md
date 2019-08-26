---
title: Практическое руководство. Совместное использование сборки с другими приложениями (C#)
ms.date: 07/20/2015
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: 954db3fe139ff307386fc182dbf16c60ce86bd30
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595733"
---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a><span data-ttu-id="3797b-102">Практическое руководство. Совместное использование сборки с другими приложениями (C#)</span><span class="sxs-lookup"><span data-stu-id="3797b-102">How to: Share an Assembly with Other Applications (C#)</span></span>
<span data-ttu-id="3797b-103">Сборки могут быть закрытыми или общими. По умолчанию большинство простых программ состоят из закрытой сборки, так как она не предназначена для использования другими приложениями.</span><span class="sxs-lookup"><span data-stu-id="3797b-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="3797b-104">Для совместного использования сборки с другими приложениями ее необходимо поместить в [глобальный кэш сборок](../../../../framework/app-domains/gac.md) (GAC).</span><span class="sxs-lookup"><span data-stu-id="3797b-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="3797b-105">Предоставление общего доступа к сборке</span><span class="sxs-lookup"><span data-stu-id="3797b-105">Sharing an assembly</span></span>  
  
1. <span data-ttu-id="3797b-106">Создайте сборку.</span><span class="sxs-lookup"><span data-stu-id="3797b-106">Create your assembly.</span></span> <span data-ttu-id="3797b-107">Дополнительные сведения см. в разделе [Создание сборок](../../../../framework/app-domains/create-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="3797b-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2. <span data-ttu-id="3797b-108">Назначьте сборке строгое имя.</span><span class="sxs-lookup"><span data-stu-id="3797b-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="3797b-109">Дополнительные сведения см. в разделе [Практическое руководство. Подписание сборки строгим именем](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="3797b-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3. <span data-ttu-id="3797b-110">Назначьте сведения о версии для сборки.</span><span class="sxs-lookup"><span data-stu-id="3797b-110">Assign version information to your assembly.</span></span> <span data-ttu-id="3797b-111">Дополнительные сведения см. в разделе [Версии сборок](../../../../framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="3797b-111">For more information, see [Assembly Versioning](../../../../framework/app-domains/assembly-versioning.md).</span></span>  
  
4. <span data-ttu-id="3797b-112">Добавьте сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="3797b-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="3797b-113">Дополнительные сведения см. в разделе [Практическое руководство. Установка сборки в глобальный кэш сборок](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="3797b-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5. <span data-ttu-id="3797b-114">Получите доступ к типам, содержащимся в сборке, из других приложений.</span><span class="sxs-lookup"><span data-stu-id="3797b-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="3797b-115">Дополнительные сведения см. в разделе [Практическое руководство. Создание ссылки на сборку со строгим именем](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="3797b-115">For more information, see [How to: Reference a Strong-Named Assembly](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3797b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3797b-116">See also</span></span>

- [<span data-ttu-id="3797b-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3797b-117">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="3797b-118">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="3797b-118">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
