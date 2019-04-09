---
title: Практическое руководство. Открывать файлы с помощью компонента OpenFileDialog
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 7f4e96f1714a182647665f12e29d38f2b8037478
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159111"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="1499e-102">Практическое руководство. Открытие файлов с использованием OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="1499e-102">How to: Open files with the OpenFileDialog</span></span> 

<span data-ttu-id="1499e-103"><xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> Компонент открывает диалоговое окно Windows для просмотра и выбора файлов.</span><span class="sxs-lookup"><span data-stu-id="1499e-103">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="1499e-104">Чтобы открыть и прочитать выбранных файлов, можно использовать <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> метод, или создать экземпляр <xref:System.IO.StreamReader?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="1499e-104">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="1499e-105">В следующих примерах оба подхода.</span><span class="sxs-lookup"><span data-stu-id="1499e-105">The following examples show both approaches.</span></span> 

<span data-ttu-id="1499e-106">В .NET Framework, для получения или задания <xref:System.Windows.Forms.FileDialog.FileName%2A> свойство требуется уровень привилегий предоставляемый <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="1499e-106">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="1499e-107">Примеры выполняют <xref:System.Security.Permissions.FileIOPermission> разрешение проверки и может создавать исключения из-за недостатка привилегий, если выполняются в контексте частичного доверия.</span><span class="sxs-lookup"><span data-stu-id="1499e-107">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="1499e-108">Дополнительные сведения см. в разделе [основы управления доступом для кода](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="1499e-108">For more information, see [Code access security basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="1499e-109">Можно создавать и запускать эти примеры приложений .NET Framework из C# или командной строки Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1499e-109">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="1499e-110">Дополнительные сведения см. в разделе [сборка с помощью csc.exe из командной строки](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) или [построения из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="1499e-110">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span> 

<span data-ttu-id="1499e-111">Начиная с .NET Core 3.0, вы можете также создавать и выполнять примеры как Windows приложений .NET Core из папки с .NET Core Windows Forms  *\<имя_папки > .csproj* файл проекта.</span><span class="sxs-lookup"><span data-stu-id="1499e-111">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span> 

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="1499e-112">Пример Чтение файла в виде потока с помощью StreamReader</span><span class="sxs-lookup"><span data-stu-id="1499e-112">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="1499e-113">В следующем примере используется Windows Forms <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Click> обработчик событий, чтобы открыть <xref:System.Windows.Forms.OpenFileDialog> с <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1499e-113">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="1499e-114">Когда пользователь выберет файл, а также выбирает **ОК**, экземпляр <xref:System.IO.StreamReader> класс читает файл и выведет его содержимое в текстовое поле формы.</span><span class="sxs-lookup"><span data-stu-id="1499e-114">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="1499e-115">Дополнительные сведения о чтении из файловых потоков, см. в разделе <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> и <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1499e-115">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="1499e-116">Пример Откройте файл из отфильтрованные объекты с помощью OpenFile</span><span class="sxs-lookup"><span data-stu-id="1499e-116">Example: Open a file from a filtered selection with OpenFile</span></span> 

<span data-ttu-id="1499e-117">В следующем примере используется <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Click> обработчик событий, чтобы открыть <xref:System.Windows.Forms.OpenFileDialog> с фильтром, который показывает только текстовые файлы.</span><span class="sxs-lookup"><span data-stu-id="1499e-117">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="1499e-118">Когда пользователь выберет в текстовый файл, а также выбирает **ОК**, <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> метод используется, чтобы открыть файл в блокноте.</span><span class="sxs-lookup"><span data-stu-id="1499e-118">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="1499e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1499e-119">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="1499e-120">OpenFileDialog - компонент</span><span class="sxs-lookup"><span data-stu-id="1499e-120">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
