---
title: "Практическое руководство: совместное использование сборки с другими приложениями (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ceebb3934c269284db18c9ca8e561417eaf5baa1
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="a9a58-102">Практическое руководство: совместное использование сборки с другими приложениями (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9a58-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="a9a58-103">Сборки могут быть закрытыми или общими: по умолчанию, большинство простой программы состоят из закрытой сборки, так как они не предназначены для использования другими приложениями.</span><span class="sxs-lookup"><span data-stu-id="a9a58-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="a9a58-104">Для совместного использования сборки с другими приложениями, он должен быть помещен в [глобального кэша сборок](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202) (GAC).</span><span class="sxs-lookup"><span data-stu-id="a9a58-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="a9a58-105">Совместное использование сборки</span><span class="sxs-lookup"><span data-stu-id="a9a58-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="a9a58-106">Создайте сборку.</span><span class="sxs-lookup"><span data-stu-id="a9a58-106">Create your assembly.</span></span> <span data-ttu-id="a9a58-107">Дополнительные сведения см. в разделе [Создание сборки](http://msdn.microsoft.com/library/54832ee9-dca8-4c8b-913c-c0b9d265e9a4).</span><span class="sxs-lookup"><span data-stu-id="a9a58-107">For more information, see [Creating Assemblies](http://msdn.microsoft.com/library/54832ee9-dca8-4c8b-913c-c0b9d265e9a4).</span></span>  
  
2.  <span data-ttu-id="a9a58-108">Назначьте строгое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="a9a58-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="a9a58-109">Дополнительные сведения см. в разделе [как: подписать сборку строгим именем](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67).</span><span class="sxs-lookup"><span data-stu-id="a9a58-109">For more information, see [How to: Sign an Assembly with a Strong Name](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67).</span></span>  
  
3.  <span data-ttu-id="a9a58-110">Укажите сведения о версии для сборки.</span><span class="sxs-lookup"><span data-stu-id="a9a58-110">Assign version information to your assembly.</span></span> <span data-ttu-id="a9a58-111">Дополнительные сведения см. в разделе [управление версиями сборок](https://msdn.microsoft.com/library/51ket42z).</span><span class="sxs-lookup"><span data-stu-id="a9a58-111">For more information, see [Assembly Versioning](https://msdn.microsoft.com/library/51ket42z).</span></span>  
  
4.  <span data-ttu-id="a9a58-112">Добавьте сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="a9a58-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="a9a58-113">Дополнительные сведения см. в разделе [Практическое руководство: Установка сборки в глобальный кэш сборок](http://msdn.microsoft.com/library/a7e6f091-d02c-49ba-b736-7295cb0eb743).</span><span class="sxs-lookup"><span data-stu-id="a9a58-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](http://msdn.microsoft.com/library/a7e6f091-d02c-49ba-b736-7295cb0eb743).</span></span>  
  
5.  <span data-ttu-id="a9a58-114">Доступ к типам, содержащихся в сборке из других приложений.</span><span class="sxs-lookup"><span data-stu-id="a9a58-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="a9a58-115">Дополнительные сведения см. в разделе [как: ссылки на сборку со строгими именами](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span><span class="sxs-lookup"><span data-stu-id="a9a58-115">For more information, see [How to: Reference a Strong-Named Assembly](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9a58-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a9a58-116">See Also</span></span>  
 <span data-ttu-id="a9a58-117">[Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)
 [сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="a9a58-117">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md)
 [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="a9a58-118"> [Программирование с использованием сборок](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)</span><span class="sxs-lookup"><span data-stu-id="a9a58-118"> [Programming with Assemblies](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)</span></span>
