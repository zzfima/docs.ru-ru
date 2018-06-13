---
title: -target:appcontainerexe (параметры компилятора C#)
ms.date: 07/20/2015
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
ms.openlocfilehash: b8765f64aeb08d816ca17fce64c13e981d85145b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216743"
---
# <a name="-targetappcontainerexe-c-compiler-options"></a><span data-ttu-id="eddec-102">-target:appcontainerexe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="eddec-102">-target:appcontainerexe (C# Compiler Options)</span></span>
<span data-ttu-id="eddec-103">Если используется параметр компилятора **-target:appcontainerexe**, компилятор создает исполняемый файл Windows (EXE-файл), который должен запускаться в контейнере приложения.</span><span class="sxs-lookup"><span data-stu-id="eddec-103">If you use the **-target:appcontainerexe** compiler option, the compiler creates a Windows executable (.exe) file that must be run in an app container.</span></span> <span data-ttu-id="eddec-104">Этот параметр аналогичен [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), но предназначен для приложений [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eddec-104">This option is equivalent to [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) but is designed for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] apps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eddec-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eddec-105">Syntax</span></span>  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="eddec-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="eddec-106">Remarks</span></span>  
 <span data-ttu-id="eddec-107">Этот параметр устанавливает бит в [переносимом исполняемом](https://msdn.microsoft.com/library/windows/desktop/ms680547(v=vs.85).aspx?id=19509) файле (PE), чтобы обеспечить запуск приложения в контейнере.</span><span class="sxs-lookup"><span data-stu-id="eddec-107">To require the app to run in an app container, this option sets a bit in the [Portable Executable](https://msdn.microsoft.com/library/windows/desktop/ms680547(v=vs.85).aspx?id=19509) (PE) file.</span></span> <span data-ttu-id="eddec-108">Если он установлен, при попытке запустить исполняемый файл вне контейнера приложения методом CreateProcess будет возникать ошибка.</span><span class="sxs-lookup"><span data-stu-id="eddec-108">When that bit is set, an error occurs if the CreateProcess method tries to launch the executable file outside an app container.</span></span>  
  
 <span data-ttu-id="eddec-109">Выходной файл получает имя входного файла, содержащего метод [Main](../../../csharp/programming-guide/main-and-command-args/index.md), если только с помощью параметра [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) не указано иное.</span><span class="sxs-lookup"><span data-stu-id="eddec-109">Unless you use the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="eddec-110">Если этот параметр указан в командной строке, все файлы до следующего параметра **-out** или **-target** будут использоваться для создания исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="eddec-110">When you specify this option at a command prompt, all files until the next **-out** or **-target** option are used to create the executable file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a><span data-ttu-id="eddec-111">Установка данного параметра компилятора в интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="eddec-111">To set this compiler option in the IDE</span></span>  
  
1.  <span data-ttu-id="eddec-112">В **обозревателе решений** откройте контекстное меню своего проекта и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="eddec-112">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="eddec-113">На вкладке **Приложение** в списке **Тип выходных данных** выберите **Приложение для Магазина Windows**.</span><span class="sxs-lookup"><span data-stu-id="eddec-113">On the **Application** tab, in the **Output type** list, choose **Windows Store App**.</span></span>  
  
     <span data-ttu-id="eddec-114">Этот параметр доступен только для шаблонов приложений под [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eddec-114">This option is available only for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] app templates.</span></span>  
  
 <span data-ttu-id="eddec-115">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="eddec-115">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eddec-116">Пример</span><span class="sxs-lookup"><span data-stu-id="eddec-116">Example</span></span>  
 <span data-ttu-id="eddec-117">Следующая команда компилирует `filename.cs` в исполняемый файл Windows, который может быть запущен только в контейнере приложения.</span><span class="sxs-lookup"><span data-stu-id="eddec-117">The following command compiles `filename.cs` into a Windows executable file that can be run only in an app container.</span></span>  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="eddec-118">См. также</span><span class="sxs-lookup"><span data-stu-id="eddec-118">See Also</span></span>  
 [<span data-ttu-id="eddec-119">-target (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="eddec-119">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="eddec-120">-target:winexe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="eddec-120">-target:winexe (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 [<span data-ttu-id="eddec-121">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="eddec-121">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
