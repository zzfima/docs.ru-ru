---
title: Образец технологии сериализации, независимой от версии
ms.date: 03/30/2017
ms.assetid: 2a183664-bfbf-4ff0-96f6-c836284ea916
ms.openlocfilehash: 996c041cd85551124fe62086e4894709183798d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="version-tolerant-serialization-technology-sample"></a><span data-ttu-id="0564a-102">Образец технологии сериализации, независимой от версии</span><span class="sxs-lookup"><span data-stu-id="0564a-102">Version Tolerant Serialization Technology Sample</span></span>
[<span data-ttu-id="0564a-103">Скачать образец</span><span class="sxs-lookup"><span data-stu-id="0564a-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/VTS.zip.exe)  
  
 <span data-ttu-id="0564a-104">В этом образце демонстрируются возможности .NET-сериализации, независимой от версии.</span><span class="sxs-lookup"><span data-stu-id="0564a-104">This sample demonstrates the version tolerance features of .NET Serialization.</span></span> <span data-ttu-id="0564a-105">В примере выполняется построение приложений, использующих различные версии объекта <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> для сериализации и десериализации данных.</span><span class="sxs-lookup"><span data-stu-id="0564a-105">The sample builds applications that use different versions of a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> to serialize and deserialize data.</span></span> <span data-ttu-id="0564a-106">Несмотря на наличие различных типов версий, приложения легко взаимодействуют друг с другом.</span><span class="sxs-lookup"><span data-stu-id="0564a-106">Despite the presence of different type versions, the applications communicate seamlessly.</span></span> <span data-ttu-id="0564a-107">Дополнительные сведения см. в разделе [Независимая от версий сериализация](../../../docs/standard/serialization/version-tolerant-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="0564a-107">For more information, see [Version Tolerant Serialization](../../../docs/standard/serialization/version-tolerant-serialization.md).</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="0564a-108">Сборка образца с использованием командной строки</span><span class="sxs-lookup"><span data-stu-id="0564a-108">To build the sample using the command prompt</span></span>  
  
1.  <span data-ttu-id="0564a-109">Откройте окно командной строки и перейдите к вложенной папке (в приложении V1 или V2) для данного образца, соответствующей выбранному языку.</span><span class="sxs-lookup"><span data-stu-id="0564a-109">Open a Command Prompt window and navigate to one of the language-specific subdirectories (under V1 Application or V2 Application) for the sample.</span></span>  
  
2.  <span data-ttu-id="0564a-110">Введите **msbuild.exe \<ver> application.sln** в командной строке (где \<ver> равно v1 или v2).</span><span class="sxs-lookup"><span data-stu-id="0564a-110">Type **msbuild.exe \<ver> application.sln** at the command line (where \<ver> is either v1 or v2).</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="0564a-111">Сборка образца с использованием Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0564a-111">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="0564a-112">Откройте [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] и перейдите к вложенной папке для данного образца, соответствующей выбранному языку.</span><span class="sxs-lookup"><span data-stu-id="0564a-112">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="0564a-113">Перейдите во вложенную папку приложения V1 из выбранного на прошлом шаге каталога.</span><span class="sxs-lookup"><span data-stu-id="0564a-113">Navigate to the V1 Application subdirectory of the directory you selected in the previous step.</span></span>  
  
3.  <span data-ttu-id="0564a-114">Дважды щелкните изображение V1 Application.sln, чтобы открыть файл в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0564a-114">Double-click the icon for V1 Application.sln to open the file in Visual Studio.</span></span>  
  
4.  <span data-ttu-id="0564a-115">В меню **Сборка** выберите **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="0564a-115">On the **Build** menu, click **Build Solution**.</span></span>  
  
5.  <span data-ttu-id="0564a-116">Перейдите во вложенную папку приложения V2 и повторите два предыдущих шага для построения приложения V2.</span><span class="sxs-lookup"><span data-stu-id="0564a-116">Navigate to the V2 Application subdirectory and repeat the two previous steps to build the V2 Application.</span></span>  
  
 <span data-ttu-id="0564a-117">По умолчанию построение приложений помещается во вложенные папки \bin или \bin\Debug каталогов соответствующего проекта.</span><span class="sxs-lookup"><span data-stu-id="0564a-117">The applications will be built in the default \bin or \bin\Debug subdirectories of their respective project directories.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="0564a-118">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="0564a-118">To run the sample</span></span>  
  
1.  <span data-ttu-id="0564a-119">В окне командной строки перейдите к одной из вложенных языковых папок, выбранных во время построения приложения.</span><span class="sxs-lookup"><span data-stu-id="0564a-119">In the Command Prompt window, navigate to the language-specific subdirectory that you selected when you built the sample applications.</span></span>  
  
2.  <span data-ttu-id="0564a-120">Введите в командной строке **runme.cmd** для одновременного выполнения обоих приложений.</span><span class="sxs-lookup"><span data-stu-id="0564a-120">Type **runme.cmd** at the command line to run both applications at once.</span></span>  
  
 <span data-ttu-id="0564a-121">Также можно перейти в каталоги, содержащие новые исполняемые файлы и последовательно выполнить их.</span><span class="sxs-lookup"><span data-stu-id="0564a-121">Alternatively, navigate to the directories that contain the new executables and run them sequentially.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0564a-122">В образце производится построение консольных приложений.</span><span class="sxs-lookup"><span data-stu-id="0564a-122">The sample builds console applications.</span></span> <span data-ttu-id="0564a-123">Чтобы просмотреть выводимые ими данные, необходимо загрузить и выполнить их в окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="0564a-123">You must launch and run them in a Command Prompt window to view their output.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0564a-124">См. также</span><span class="sxs-lookup"><span data-stu-id="0564a-124">See Also</span></span>  
 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
 <xref:System.IO.FileStream>
