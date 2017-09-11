---
title: "При компиляции XML-схем в проекте возникли ошибки | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36810
- vbc36810
dev_langs:
- VB
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7e6a835f84f2e37f4f583bc16c24cf9bb28cc92a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="acfeb-102">При компиляции XML-схем в проекте возникли ошибки</span><span class="sxs-lookup"><span data-stu-id="acfeb-102">Errors occurred while compiling the XML schemas in the project</span></span>
<span data-ttu-id="acfeb-103">При компиляции XML-схем в проекте возникли ошибки.</span><span class="sxs-lookup"><span data-stu-id="acfeb-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="acfeb-104">В результате XML IntelliSense недоступна.</span><span class="sxs-lookup"><span data-stu-id="acfeb-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="acfeb-105">Имеется ошибка в схеме определения схемы XML (XSD), включенный в проект.</span><span class="sxs-lookup"><span data-stu-id="acfeb-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="acfeb-106">Эта ошибка возникает при добавлении XSD-файл схемы (XSD), задать конфликтует с существующей схемой XSD для проекта.</span><span class="sxs-lookup"><span data-stu-id="acfeb-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="acfeb-107">**Идентификатор ошибки:** BC36810</span><span class="sxs-lookup"><span data-stu-id="acfeb-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="acfeb-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="acfeb-108">To correct this error</span></span>  
  
-   <span data-ttu-id="acfeb-109">Дважды щелкните значок предупреждения в **список ошибок** окна.</span><span class="sxs-lookup"><span data-stu-id="acfeb-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="acfeb-110">Visual Basic, вы перейдете расположение в XSD-файле, который является источником предупреждения.</span><span class="sxs-lookup"><span data-stu-id="acfeb-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="acfeb-111">Исправление ошибки в схеме XSD.</span><span class="sxs-lookup"><span data-stu-id="acfeb-111">Correct the error in the XSD schema.</span></span>  
  
-   <span data-ttu-id="acfeb-112">Убедитесь, что все необходимые файлы XSD-схемы (.xsd) включены в проект.</span><span class="sxs-lookup"><span data-stu-id="acfeb-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="acfeb-113">Может потребоваться нажать **Показать все файлы** на **проекта** меню для просмотра вашего .xsd файлы в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="acfeb-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="acfeb-114">Щелкните правой кнопкой мыши XSD-файл и нажмите кнопку **включить в проект** для включения файла в проект.</span><span class="sxs-lookup"><span data-stu-id="acfeb-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
-   <span data-ttu-id="acfeb-115">При использовании XML для мастера схем это ошибка может возникать, если схемы были получены более одного раза из одного источника.</span><span class="sxs-lookup"><span data-stu-id="acfeb-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="acfeb-116">В этом случае можно удалить существующие файлы схемы XSD из проекта, добавить новый XML для шаблона элементов схемы и предоставьте XML для мастера схем всех источниками XML для проекта.</span><span class="sxs-lookup"><span data-stu-id="acfeb-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
-   <span data-ttu-id="acfeb-117">Если ошибка не найдена в схеме XSD, компилятору XML может не иметь достаточно сведений, чтобы предоставить подробные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="acfeb-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="acfeb-118">Возможно, удастся получить более подробные сведения об ошибке, если вы убедитесь, что пространства имен XML для XSD-файлы включены в проект, совпадают пространствами имен XML для XML-схемы в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="acfeb-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acfeb-119">См. также</span><span class="sxs-lookup"><span data-stu-id="acfeb-119">See Also</span></span>  
 <span data-ttu-id="acfeb-120">[Окно списка ошибок](https://docs.microsoft.com/visualstudio/ide/reference/error-list-window) </span><span class="sxs-lookup"><span data-stu-id="acfeb-120">[Error List Window](https://docs.microsoft.com/visualstudio/ide/reference/error-list-window) </span></span>  
<span data-ttu-id="acfeb-121"> [XML IntelliSense в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md) </span><span class="sxs-lookup"><span data-stu-id="acfeb-121"> [XML IntelliSense in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md) </span></span>  
<span data-ttu-id="acfeb-122"> [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)</span><span class="sxs-lookup"><span data-stu-id="acfeb-122"> [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)</span></span>
