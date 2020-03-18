---
title: -target:appcontainerexe (параметры компилятора C#)
ms.date: 07/20/2015
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
ms.openlocfilehash: 64661e72f9efe190606cadd93558678cb849e8cc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74204527"
---
# <a name="-targetappcontainerexe-c-compiler-options"></a><span data-ttu-id="7674a-102">-target:appcontainerexe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="7674a-102">-target:appcontainerexe (C# Compiler Options)</span></span>
<span data-ttu-id="7674a-103">Если используется параметр компилятора **-target:appcontainerexe**, компилятор создает исполняемый файл Windows (EXE-файл), который должен запускаться в контейнере приложения.</span><span class="sxs-lookup"><span data-stu-id="7674a-103">If you use the **-target:appcontainerexe** compiler option, the compiler creates a Windows executable (.exe) file that must be run in an app container.</span></span> <span data-ttu-id="7674a-104">Этот параметр аналогичен [-target:winexe](./target-winexe-compiler-option.md), но предназначен для приложений Магазина Windows 8.x.</span><span class="sxs-lookup"><span data-stu-id="7674a-104">This option is equivalent to [-target:winexe](./target-winexe-compiler-option.md) but is designed for Windows 8.x Store apps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7674a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7674a-105">Syntax</span></span>  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="7674a-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="7674a-106">Remarks</span></span>  
 <span data-ttu-id="7674a-107">Этот параметр устанавливает бит в [переносимом исполняемом](/windows/desktop/Debug/pe-format) файле (PE), чтобы обеспечить запуск приложения в контейнере.</span><span class="sxs-lookup"><span data-stu-id="7674a-107">To require the app to run in an app container, this option sets a bit in the [Portable Executable](/windows/desktop/Debug/pe-format) (PE) file.</span></span> <span data-ttu-id="7674a-108">Если он установлен, при попытке запустить исполняемый файл вне контейнера приложения методом CreateProcess будет возникать ошибка.</span><span class="sxs-lookup"><span data-stu-id="7674a-108">When that bit is set, an error occurs if the CreateProcess method tries to launch the executable file outside an app container.</span></span>  
  
 <span data-ttu-id="7674a-109">Выходной файл получает имя входного файла, содержащего метод [Main](./out-compiler-option.md), если только с помощью параметра [-out](../../programming-guide/main-and-command-args/index.md) не указано иное.</span><span class="sxs-lookup"><span data-stu-id="7674a-109">Unless you use the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="7674a-110">Если этот параметр указан в командной строке, все файлы до следующего параметра **-out** или **-target** будут использоваться для создания исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="7674a-110">When you specify this option at a command prompt, all files until the next **-out** or **-target** option are used to create the executable file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a><span data-ttu-id="7674a-111">Установка данного параметра компилятора в интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="7674a-111">To set this compiler option in the IDE</span></span>  
  
1. <span data-ttu-id="7674a-112">В **обозревателе решений** откройте контекстное меню своего проекта и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7674a-112">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="7674a-113">На вкладке **Приложение** в списке **Тип выходных данных** выберите **Приложение для Магазина Windows**.</span><span class="sxs-lookup"><span data-stu-id="7674a-113">On the **Application** tab, in the **Output type** list, choose **Windows Store App**.</span></span>  
  
     <span data-ttu-id="7674a-114">Этот параметр доступен только для шаблонов приложений Магазина Windows 8.x.</span><span class="sxs-lookup"><span data-stu-id="7674a-114">This option is available only for Windows 8.x Store app templates.</span></span>  
  
 <span data-ttu-id="7674a-115">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="7674a-115">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7674a-116">Пример</span><span class="sxs-lookup"><span data-stu-id="7674a-116">Example</span></span>  
 <span data-ttu-id="7674a-117">Следующая команда компилирует `filename.cs` в исполняемый файл Windows, который может быть запущен только в контейнере приложения.</span><span class="sxs-lookup"><span data-stu-id="7674a-117">The following command compiles `filename.cs` into a Windows executable file that can be run only in an app container.</span></span>  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="7674a-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7674a-118">See also</span></span>

- [<span data-ttu-id="7674a-119">-target (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="7674a-119">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="7674a-120">-target:winexe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="7674a-120">-target:winexe (C# Compiler Options)</span></span>](./target-winexe-compiler-option.md)
- [<span data-ttu-id="7674a-121">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="7674a-121">C# Compiler Options</span></span>](./index.md)
