---
title: Требуется ссылка на сборку <assemblyname>, содержащую базовый класс <classname>
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: 8218a3325d5d47bf85aacab1724221d233d92ba4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661706"
---
# <a name="reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a><span data-ttu-id="195f3-102">Требуется ссылка на сборку "\<имя_сборки >" содержит базовый класс\<имя_класса > "</span><span class="sxs-lookup"><span data-stu-id="195f3-102">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'</span></span>
<span data-ttu-id="195f3-103">Требуется ссылка на сборку "\<имя_сборки >" содержит базовый класс\<имя_класса > ".</span><span class="sxs-lookup"><span data-stu-id="195f3-103">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="195f3-104">Добавьте эту ссылку в проект.</span><span class="sxs-lookup"><span data-stu-id="195f3-104">Add one to your project.</span></span>  
  
 <span data-ttu-id="195f3-105">Класс определяется в библиотеке динамической компоновки (DLL) или в сборке, на которую в проекте нет прямой ссылки.</span><span class="sxs-lookup"><span data-stu-id="195f3-105">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="195f3-106">Компилятор Visual Basic требует ссылку, чтобы исключить неоднозначность в случае, если класс определен в нескольких библиотеках DLL или сборках.</span><span class="sxs-lookup"><span data-stu-id="195f3-106">The Visual Basic compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>  
  
 <span data-ttu-id="195f3-107">**Идентификатор ошибки:** BC30007</span><span class="sxs-lookup"><span data-stu-id="195f3-107">**Error ID:** BC30007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="195f3-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="195f3-108">To correct this error</span></span>  
  
- <span data-ttu-id="195f3-109">Включите в ссылки проекта имя библиотеки DLL или сборки, на которую нет ссылки.</span><span class="sxs-lookup"><span data-stu-id="195f3-109">Include the name of the unreferenced DLL or assembly in your project references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195f3-110">См. также</span><span class="sxs-lookup"><span data-stu-id="195f3-110">See also</span></span>

- [<span data-ttu-id="195f3-111">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="195f3-111">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="195f3-112">Диагностика неработающих ссылок</span><span class="sxs-lookup"><span data-stu-id="195f3-112">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
