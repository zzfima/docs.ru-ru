---
title: Образец технологии SchemaImporterExtension
ms.date: 03/30/2017
ms.assetid: 3f5eb78f-0ef6-433a-b095-3a63b1ce0bc9
ms.openlocfilehash: 042ea9eecb7820d4ffb88bdb8862aec1e7f6e483
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042495"
---
# <a name="schemaimporterextension-technology-sample"></a><span data-ttu-id="3b265-102">Образец технологии SchemaImporterExtension</span><span class="sxs-lookup"><span data-stu-id="3b265-102">SchemaImporterExtension Technology Sample</span></span>
[<span data-ttu-id="3b265-103">Скачать образец</span><span class="sxs-lookup"><span data-stu-id="3b265-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/SchemaImporterExtension.zip.exe)  
  
 <span data-ttu-id="3b265-104">В этом образце демонстрируется пользовательский класс <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>, позволяющий более точно управлять формированием кода при импорте схемы XML.</span><span class="sxs-lookup"><span data-stu-id="3b265-104">This sample demonstrates a custom <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> that allows fine control over code generation when an XML schema is imported.</span></span> <span data-ttu-id="3b265-105">C помощью этого приложения показывается, как выполнять построение, регистрировать и вызывать это расширение.</span><span class="sxs-lookup"><span data-stu-id="3b265-105">The application shows how to build, register and invoke this extension.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="3b265-106">Сборка образца с использованием командной строки</span><span class="sxs-lookup"><span data-stu-id="3b265-106">To build the sample using the command prompt</span></span>  
  
1.  <span data-ttu-id="3b265-107">Откройте окно командной строки и перейдите к вложенной папке для данного образца, соответствующей выбранному языку.</span><span class="sxs-lookup"><span data-stu-id="3b265-107">Open a Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="3b265-108">В командной строке введите **msbuild.exe OrderSchemaImporterExtension.sln**.</span><span class="sxs-lookup"><span data-stu-id="3b265-108">Type **msbuild.exe OrderSchemaImporterExtension.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="3b265-109">Сборка образца с использованием Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3b265-109">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="3b265-110">Откройте [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] и перейдите к вложенной папке для данного образца, соответствующей выбранному языку.</span><span class="sxs-lookup"><span data-stu-id="3b265-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="3b265-111">Дважды щелкните значок OrderSchemaImporterExtension.sln, чтобы открыть файл в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3b265-111">Double-click the icon for OrderSchemaImporterExtension.sln to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="3b265-112">В меню **Сборка** выберите **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="3b265-112">On the **Build** menu, click **Build Solution**.</span></span>  
  
 <span data-ttu-id="3b265-113">По умолчанию построение приложения помещается в каталог \bin или \bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="3b265-113">The application will be built in the default \bin or \bin\Debug directory.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="3b265-114">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="3b265-114">To run the sample</span></span>  
  
1.  <span data-ttu-id="3b265-115">С помощью командной строки перейдите в каталог, содержащий новый исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="3b265-115">Navigate to the directory containing the new executable, using the command prompt.</span></span>  
  
2.  <span data-ttu-id="3b265-116">В командной строке введите **[exe имя]**.</span><span class="sxs-lookup"><span data-stu-id="3b265-116">Type **[exe name]** at the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b265-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="3b265-117">Remarks</span></span>  
 <span data-ttu-id="3b265-118">Дополнительные сведения о создании примера двоичного файла и шагах по его регистрации см. в комментариях в файле исходного кода и файле build.proj.</span><span class="sxs-lookup"><span data-stu-id="3b265-118">For more information about sample binary creation and registration steps, see the comments in the source code and build.proj files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b265-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3b265-119">See also</span></span>

- <xref:System.CodeDom.CodeCompileUnit>  
- <xref:System.CodeDom.CodeNamespace>  
- <xref:System.CodeDom.CodeNamespaceImport>  
- <xref:Microsoft.CSharp.CSharpCodeProvider>  
- <xref:System.Xml.Serialization.IXmlSerializable>  
- <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>  
- <xref:System.CodeDom>  
- <xref:System.CodeDom.Compiler>  
- <xref:System.Web.Services.Description>  
- <xref:System.Web.Services.Discovery>  
- <xref:System.Xml.Serialization>  
- <xref:System.Uri>  
- <xref:Microsoft.VisualBasic.VBCodeProvider>  
- <xref:System.Web.Services.Description.WebReference>  
- <xref:System.Xml.Serialization.XmlSchemaImporter>
