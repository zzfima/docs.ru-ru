---
title: "-target:appcontainerexe (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9ab407f14483bbb5abaf3dc23b0cf204091b74ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="targetappcontainerexe-c-compiler-options"></a><span data-ttu-id="578d8-102">/target:appcontainerexe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="578d8-102">/target:appcontainerexe (C# Compiler Options)</span></span>
<span data-ttu-id="578d8-103">Если используется параметр компилятора **/target:appcontainerexe**, компилятор создает исполняемый файл Windows (EXE-файл), который должен запускаться в контейнере приложения.</span><span class="sxs-lookup"><span data-stu-id="578d8-103">If you use the **/target:appcontainerexe** compiler option, the compiler creates a Windows executable (.exe) file that must be run in an app container.</span></span> <span data-ttu-id="578d8-104">Этот параметр аналогичен [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), но предназначен для приложений [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="578d8-104">This option is equivalent to [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) but is designed for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] apps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="578d8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="578d8-105">Syntax</span></span>  
  
```console  
/target:appcontainerexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="578d8-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="578d8-106">Remarks</span></span>  
 <span data-ttu-id="578d8-107">Этот параметр устанавливает бит в [переносимом исполняемом](http://go.microsoft.com/fwlink/p/?LinkId=236960) файле (PE), чтобы обеспечить запуск приложения в контейнере.</span><span class="sxs-lookup"><span data-stu-id="578d8-107">To require the app to run in an app container, this option sets a bit in the [Portable Executable](http://go.microsoft.com/fwlink/p/?LinkId=236960) (PE) file.</span></span> <span data-ttu-id="578d8-108">Если он установлен, при попытке запустить исполняемый файл вне контейнера приложения методом CreateProcess будет возникать ошибка.</span><span class="sxs-lookup"><span data-stu-id="578d8-108">When that bit is set, an error occurs if the CreateProcess method tries to launch the executable file outside an app container.</span></span>  
  
 <span data-ttu-id="578d8-109">Выходной файл получает имя входного файла, содержащего метод [Main](../../../csharp/programming-guide/main-and-command-args/index.md), если только с помощью параметра [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) не указано иное.</span><span class="sxs-lookup"><span data-stu-id="578d8-109">Unless you use the [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="578d8-110">Если этот параметр указан в командной строке, все файлы до следующего параметра **/out** или **/target** будут использоваться для создания исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="578d8-110">When you specify this option at a command prompt, all files until the next **/out** or **/target** option are used to create the executable file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a><span data-ttu-id="578d8-111">Установка данного параметра компилятора в интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="578d8-111">To set this compiler option in the IDE</span></span>  
  
1.  <span data-ttu-id="578d8-112">В **обозревателе решений** откройте контекстное меню своего проекта и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="578d8-112">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="578d8-113">На вкладке **Приложение** в списке **Тип выходных данных** выберите **Приложение для Магазина Windows**.</span><span class="sxs-lookup"><span data-stu-id="578d8-113">On the **Application** tab, in the **Output type** list, choose **Windows Store App**.</span></span>  
  
     <span data-ttu-id="578d8-114">Этот параметр доступен только для шаблонов приложений под [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="578d8-114">This option is available only for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] app templates.</span></span>  
  
 <span data-ttu-id="578d8-115">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="578d8-115">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="578d8-116">Пример</span><span class="sxs-lookup"><span data-stu-id="578d8-116">Example</span></span>  
 <span data-ttu-id="578d8-117">Следующая команда компилирует `filename.cs` в исполняемый файл Windows, который может быть запущен только в контейнере приложения.</span><span class="sxs-lookup"><span data-stu-id="578d8-117">The following command compiles `filename.cs` into a Windows executable file that can be run only in an app container.</span></span>  
  
```console  
csc /target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="578d8-118">См. также</span><span class="sxs-lookup"><span data-stu-id="578d8-118">See Also</span></span>  
 [<span data-ttu-id="578d8-119">/ Target (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="578d8-119">/target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="578d8-120">/ target: winexe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="578d8-120">/target:winexe (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 [<span data-ttu-id="578d8-121">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="578d8-121">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
