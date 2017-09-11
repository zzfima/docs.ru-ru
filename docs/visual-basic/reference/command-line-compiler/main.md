---
title: "/ main | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: 19
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
ms.openlocfilehash: 61aa78e131ba8903035f630a540f49848f1acd3f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="main"></a><span data-ttu-id="cc889-102">/main</span><span class="sxs-lookup"><span data-stu-id="cc889-102">/main</span></span>
<span data-ttu-id="cc889-103">Указывает класс или модуль, содержащий `Sub Main` процедуры.</span><span class="sxs-lookup"><span data-stu-id="cc889-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc889-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc889-104">Syntax</span></span>  
  
```  
/main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="cc889-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cc889-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="cc889-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="cc889-106">Required.</span></span> <span data-ttu-id="cc889-107">Полное имя пространства имен для класса или модуля, содержащего `Sub Main` процедуры, который должен вызываться при запуске программы.</span><span class="sxs-lookup"><span data-stu-id="cc889-107">A full qualification to the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="cc889-108">Это может быть в форме **/main:module** или **/main:namespace.module**.</span><span class="sxs-lookup"><span data-stu-id="cc889-108">This may be in the form **/main:module** or **/main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc889-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc889-109">Remarks</span></span>  
 <span data-ttu-id="cc889-110">Используйте этот параметр при создании исполняемого файла или программы для Windows.</span><span class="sxs-lookup"><span data-stu-id="cc889-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="cc889-111">Если **/main** параметр указан, компилятор выполняет поиск допустимый общий `Sub Main` во всех открытых классов и модулей.</span><span class="sxs-lookup"><span data-stu-id="cc889-111">If the **/main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="cc889-112">В разделе [процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) обсуждение различных видов `Main` процедуры.</span><span class="sxs-lookup"><span data-stu-id="cc889-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="cc889-113">Когда `location` — это класс, который наследует от <xref:System.Windows.Forms.Form>, компилятор предоставляет значение по умолчанию `Main` процедуру, которая запускает приложение, если класс не имеет `Main` процедуры.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="cc889-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="cc889-114">Это позволяет скомпилировать код из командной строки, который был создан в среде разработки.</span><span class="sxs-lookup"><span data-stu-id="cc889-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 <span data-ttu-id="cc889-115">[!code-vb[VbVbalrCompiler №&16;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="cc889-115">[!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]</span></span>  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="cc889-116">Чтобы установить параметр/Main в Visual Studio интегрированная среда разработки</span><span class="sxs-lookup"><span data-stu-id="cc889-116">To set /main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="cc889-117">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="cc889-117">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="cc889-118">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="cc889-118">On the **Project** menu, click **Properties**.</span></span>  
  
     <span data-ttu-id="cc889-119">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="cc889-119">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="cc889-120">Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="cc889-120">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="cc889-121">Убедитесь, что **Включить исполняющую среду** не установлен флажок.</span><span class="sxs-lookup"><span data-stu-id="cc889-121">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="cc889-122">Измените значение в **автоматически запускаемый объект** поле.</span><span class="sxs-lookup"><span data-stu-id="cc889-122">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc889-123">Пример</span><span class="sxs-lookup"><span data-stu-id="cc889-123">Example</span></span>  
 <span data-ttu-id="cc889-124">Следующий код компилирует `T2.vb` и `T3.vb`, указав, `Sub Main` процедуры будут находиться в `Test2` класса.</span><span class="sxs-lookup"><span data-stu-id="cc889-124">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc889-125">См. также</span><span class="sxs-lookup"><span data-stu-id="cc889-125">See Also</span></span>  
 <span data-ttu-id="cc889-126">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="cc889-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="cc889-127"> [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="cc889-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="cc889-128"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="cc889-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="cc889-129"> [NIB: версия Visual Basic Hello World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c) </span><span class="sxs-lookup"><span data-stu-id="cc889-129"> [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c) </span></span>  
<span data-ttu-id="cc889-130"> [Процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)</span><span class="sxs-lookup"><span data-stu-id="cc889-130"> [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)</span></span>
