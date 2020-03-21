---
title: 'Как: Открыть файлы с компонентом OpenFileDialog'
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: ca69de19ab1b9ae387002898145fe99e35a7b6b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182134"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="a0ff1-102">Как: Открыть файлы с OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="a0ff1-102">How to: Open files with the OpenFileDialog</span></span>

<span data-ttu-id="a0ff1-103">Компонент <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> открывает диалоговое окно Windows для просмотра и выбора файлов.</span><span class="sxs-lookup"><span data-stu-id="a0ff1-103">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="a0ff1-104">Чтобы открыть и прочитать выбранные файлы, можно использовать <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> метод <xref:System.IO.StreamReader?displayProperty=nameWithType> или создать экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="a0ff1-104">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a0ff1-105">Следующие примеры показывают оба подхода.</span><span class="sxs-lookup"><span data-stu-id="a0ff1-105">The following examples show both approaches.</span></span>

<span data-ttu-id="a0ff1-106">В рамках .NET для получения <xref:System.Windows.Forms.FileDialog.FileName%2A> или установки свойства <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> требуется уровень привилегий, предоставляемый классом.</span><span class="sxs-lookup"><span data-stu-id="a0ff1-106">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a0ff1-107">Примеры выполнить проверку разрешений <xref:System.Security.Permissions.FileIOPermission> и могут выбросить исключение из-за недостаточной привилегий, если они работают в контексте частичного доверия.</span><span class="sxs-lookup"><span data-stu-id="a0ff1-107">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="a0ff1-108">Для получения дополнительной [информации](../../misc/code-access-security-basics.md)см.</span><span class="sxs-lookup"><span data-stu-id="a0ff1-108">For more information, see [Code access security basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="a0ff1-109">Вы можете создавать и запускать эти примеры в виде приложений .NET Framework из командной строки C- или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a0ff1-109">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="a0ff1-110">Для получения дополнительной информации [см.](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)</span><span class="sxs-lookup"><span data-stu-id="a0ff1-110">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>

<span data-ttu-id="a0ff1-111">Начиная с .NET Core 3.0, вы также можете создавать и запускать примеры приложений Windows .NET Core из папки с названием папки .NET Core Windows Forms \* \<>.csproj\* project file.</span><span class="sxs-lookup"><span data-stu-id="a0ff1-111">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span>

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="a0ff1-112">Пример: Прочитайте файл как поток с StreamReader</span><span class="sxs-lookup"><span data-stu-id="a0ff1-112">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="a0ff1-113">В следующем примере <xref:System.Windows.Forms.Button> используется обработчик <xref:System.Windows.Forms.Control.Click> событий <xref:System.Windows.Forms.OpenFileDialog> управления <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Windows Forms, чтобы открыть метод.</span><span class="sxs-lookup"><span data-stu-id="a0ff1-113">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="a0ff1-114">После того, как пользователь выбирает файл и выбирает <xref:System.IO.StreamReader> **OK,** экземпляр класса читает файл и отображает его содержимое в текстовом поле формы.</span><span class="sxs-lookup"><span data-stu-id="a0ff1-114">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="a0ff1-115">Для получения дополнительной информации о <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> чтении из файлов потоков, см. <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a0ff1-115">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="a0ff1-116">Пример: Откройте файл из фильтрованного выбора с помощью OpenFile</span><span class="sxs-lookup"><span data-stu-id="a0ff1-116">Example: Open a file from a filtered selection with OpenFile</span></span>

<span data-ttu-id="a0ff1-117">В следующем примере используется <xref:System.Windows.Forms.Control.Click> обработчик <xref:System.Windows.Forms.OpenFileDialog> событий <xref:System.Windows.Forms.Button> элемента управления для открытия фильтра, отображающего только текстовые файлы.</span><span class="sxs-lookup"><span data-stu-id="a0ff1-117">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="a0ff1-118">После того, как пользователь выбирает текстовый <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> файл и выбирает **OK,** метод используется для открытия файла в блокноте.</span><span class="sxs-lookup"><span data-stu-id="a0ff1-118">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="a0ff1-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a0ff1-119">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="a0ff1-120">Компонент OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="a0ff1-120">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
