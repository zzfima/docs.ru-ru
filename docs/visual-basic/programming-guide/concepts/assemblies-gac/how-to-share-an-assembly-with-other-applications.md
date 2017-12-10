---
title: "Как: совместное использование сборки с другими приложениями (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0ad7a3f2ee82d0a582e755035448d565a9a8cb9d
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="cbc64-102">Как: совместное использование сборки с другими приложениями (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbc64-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="cbc64-103">Сборки могут быть закрытыми или общими. По умолчанию большинство простых программ состоят из закрытой сборки, так как она не предназначена для использования другими приложениями.</span><span class="sxs-lookup"><span data-stu-id="cbc64-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="cbc64-104">Для совместного использования сборки с другими приложениями ее необходимо поместить в [глобальный кэш сборок](../../../../framework/app-domains/gac.md) (GAC).</span><span class="sxs-lookup"><span data-stu-id="cbc64-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="cbc64-105">Предоставление общего доступа к сборке</span><span class="sxs-lookup"><span data-stu-id="cbc64-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="cbc64-106">Создайте сборку.</span><span class="sxs-lookup"><span data-stu-id="cbc64-106">Create your assembly.</span></span> <span data-ttu-id="cbc64-107">Дополнительные сведения см. в разделе [Создание сборок](../../../../framework/app-domains/create-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="cbc64-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="cbc64-108">Назначьте сборке строгое имя.</span><span class="sxs-lookup"><span data-stu-id="cbc64-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="cbc64-109">Дополнительные сведения см. в разделе [Практическое руководство. Подписание сборки строгим именем](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="cbc64-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="cbc64-110">Назначьте сведения о версии для сборки.</span><span class="sxs-lookup"><span data-stu-id="cbc64-110">Assign version information to your assembly.</span></span> <span data-ttu-id="cbc64-111">Дополнительные сведения см. в разделе [Версии сборок](../../../../../docs/framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="cbc64-111">For more information, see [Assembly Versioning](../../../../../docs/framework/app-domains/assembly-versioning.md).</span></span>  
  
4.  <span data-ttu-id="cbc64-112">Добавьте сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="cbc64-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="cbc64-113">Дополнительные сведения см. в разделе [Практическое руководство. Установка сборки в глобальный кэш сборок](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="cbc64-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="cbc64-114">Получите доступ к типам, содержащимся в сборке, из других приложений.</span><span class="sxs-lookup"><span data-stu-id="cbc64-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="cbc64-115">Дополнительные сведения см. в разделе [Практическое руководство. Создание ссылки на сборку со строгим именем](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span><span class="sxs-lookup"><span data-stu-id="cbc64-115">For more information, see [How to: Reference a Strong-Named Assembly](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc64-116">См. также</span><span class="sxs-lookup"><span data-stu-id="cbc64-116">See Also</span></span>  
 <span data-ttu-id="cbc64-117">[Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md) [сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)</span><span class="sxs-lookup"><span data-stu-id="cbc64-117">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)</span></span>  
 [<span data-ttu-id="cbc64-118">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="cbc64-118">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
