---
title: /main
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2697b837a536b1b879196bd10843a2b76314747a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="main"></a><span data-ttu-id="34c3e-102">/main</span><span class="sxs-lookup"><span data-stu-id="34c3e-102">/main</span></span>
<span data-ttu-id="34c3e-103">Задает класс или модуль, содержащий процедуру `Sub Main`.</span><span class="sxs-lookup"><span data-stu-id="34c3e-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34c3e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34c3e-104">Syntax</span></span>  
  
```  
/main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="34c3e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="34c3e-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="34c3e-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="34c3e-106">Required.</span></span> <span data-ttu-id="34c3e-107">Полное имя пространства имен к классу или модулю, содержащему `Sub Main` процедура вызывается при запуске программы.</span><span class="sxs-lookup"><span data-stu-id="34c3e-107">A full qualification to the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="34c3e-108">Это может быть в форме **/main:module** или **/main:namespace.module**.</span><span class="sxs-lookup"><span data-stu-id="34c3e-108">This may be in the form **/main:module** or **/main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34c3e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="34c3e-109">Remarks</span></span>  
 <span data-ttu-id="34c3e-110">Используйте этот параметр при создании исполняемого файла или программы для Windows.</span><span class="sxs-lookup"><span data-stu-id="34c3e-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="34c3e-111">Если **/main** параметр опущен, компилятор выполняет поиск допустимый общий `Sub Main` во всех открытых классов и модулей.</span><span class="sxs-lookup"><span data-stu-id="34c3e-111">If the **/main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="34c3e-112">В разделе [процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) обсуждение различных видов `Main` процедуры.</span><span class="sxs-lookup"><span data-stu-id="34c3e-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="34c3e-113">Когда `location` — это класс, наследующий от <xref:System.Windows.Forms.Form>, компилятор предоставляет значение по умолчанию `Main` процедуру, которая запускает приложение, если класс не имеет `Main` процедуры.</span><span class="sxs-lookup"><span data-stu-id="34c3e-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="34c3e-114">Это позволяет компилировать код из командной строки, который был создан в среде разработки.</span><span class="sxs-lookup"><span data-stu-id="34c3e-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="34c3e-115">Задание/Main в Visual Studio интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="34c3e-115">To set /main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="34c3e-116">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="34c3e-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="34c3e-117">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="34c3e-117">On the **Project** menu, click **Properties**.</span></span>  
  
     <span data-ttu-id="34c3e-118">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="34c3e-118">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="34c3e-119">Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="34c3e-119">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="34c3e-120">Убедитесь, что **Включить исполняющую среду** не установлен флажок.</span><span class="sxs-lookup"><span data-stu-id="34c3e-120">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="34c3e-121">Измените значение в **автоматически запускаемый объект** поле.</span><span class="sxs-lookup"><span data-stu-id="34c3e-121">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34c3e-122">Пример</span><span class="sxs-lookup"><span data-stu-id="34c3e-122">Example</span></span>  
 <span data-ttu-id="34c3e-123">Следующий код компилирует `T2.vb` и `T3.vb`, указав, `Sub Main` процедуры будут находиться в `Test2` класса.</span><span class="sxs-lookup"><span data-stu-id="34c3e-123">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="34c3e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="34c3e-124">See Also</span></span>  
 [<span data-ttu-id="34c3e-125">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="34c3e-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="34c3e-126">/ Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34c3e-126">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="34c3e-127">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="34c3e-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="34c3e-128">NIB: версия Visual Basic Hello World</span><span class="sxs-lookup"><span data-stu-id="34c3e-128">NIB: Visual Basic Version of Hello, World</span></span>](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [<span data-ttu-id="34c3e-129">Процедура Main в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="34c3e-129">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
