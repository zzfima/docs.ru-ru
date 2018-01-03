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
ms.openlocfilehash: c5bb11bc62e951339113f4b48e98e05362490ca1
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="main"></a><span data-ttu-id="acd1a-102">/main</span><span class="sxs-lookup"><span data-stu-id="acd1a-102">/main</span></span>
<span data-ttu-id="acd1a-103">Задает класс или модуль, содержащий процедуру `Sub Main`.</span><span class="sxs-lookup"><span data-stu-id="acd1a-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acd1a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="acd1a-104">Syntax</span></span>  
  
```  
/main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="acd1a-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="acd1a-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="acd1a-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="acd1a-106">Required.</span></span> <span data-ttu-id="acd1a-107">Полное имя пространства имен к классу или модулю, содержащему `Sub Main` процедура вызывается при запуске программы.</span><span class="sxs-lookup"><span data-stu-id="acd1a-107">A full qualification to the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="acd1a-108">Это может быть в форме **/main:module** или **/main:namespace.module**.</span><span class="sxs-lookup"><span data-stu-id="acd1a-108">This may be in the form **/main:module** or **/main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acd1a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="acd1a-109">Remarks</span></span>  
 <span data-ttu-id="acd1a-110">Используйте этот параметр при создании исполняемого файла или программы для Windows.</span><span class="sxs-lookup"><span data-stu-id="acd1a-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="acd1a-111">Если **/main** параметр опущен, компилятор выполняет поиск допустимый общий `Sub Main` во всех открытых классов и модулей.</span><span class="sxs-lookup"><span data-stu-id="acd1a-111">If the **/main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="acd1a-112">В разделе [процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) обсуждение различных видов `Main` процедуры.</span><span class="sxs-lookup"><span data-stu-id="acd1a-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="acd1a-113">Когда `location` — это класс, наследующий от <xref:System.Windows.Forms.Form>, компилятор предоставляет значение по умолчанию `Main` процедуру, которая запускает приложение, если класс не имеет `Main` процедуры.</span><span class="sxs-lookup"><span data-stu-id="acd1a-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="acd1a-114">Это позволяет компилировать код из командной строки, который был создан в среде разработки.</span><span class="sxs-lookup"><span data-stu-id="acd1a-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="acd1a-115">Задание/Main в Visual Studio интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="acd1a-115">To set /main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="acd1a-116">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="acd1a-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="acd1a-117">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="acd1a-117">On the **Project** menu, click **Properties**.</span></span>  
  
       
  
2.  <span data-ttu-id="acd1a-118">Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="acd1a-118">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="acd1a-119">Убедитесь, что **Включить исполняющую среду** не установлен флажок.</span><span class="sxs-lookup"><span data-stu-id="acd1a-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="acd1a-120">Измените значение в **автоматически запускаемый объект** поле.</span><span class="sxs-lookup"><span data-stu-id="acd1a-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acd1a-121">Пример</span><span class="sxs-lookup"><span data-stu-id="acd1a-121">Example</span></span>  
 <span data-ttu-id="acd1a-122">Следующий код компилирует `T2.vb` и `T3.vb`, указав, `Sub Main` процедуры будут находиться в `Test2` класса.</span><span class="sxs-lookup"><span data-stu-id="acd1a-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="acd1a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="acd1a-123">See Also</span></span>  
 [<span data-ttu-id="acd1a-124">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="acd1a-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="acd1a-125">/ Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acd1a-125">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="acd1a-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="acd1a-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="acd1a-127">Процедура Main в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="acd1a-127">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
