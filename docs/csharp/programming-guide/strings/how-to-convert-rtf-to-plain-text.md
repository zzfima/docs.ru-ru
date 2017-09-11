---
title: "Практическое руководство. Преобразование формата RTF в обычный текст (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], converting from RTF
ms.assetid: 3b386a87-899d-4d98-bc82-a980526ddaac
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e4c7b48467f3b260526c604fa3a36fc5d80374e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-rtf-to-plain-text-c-programming-guide"></a><span data-ttu-id="0085b-102">Практическое руководство. Преобразование формата RTF в обычный текст (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="0085b-102">How to: Convert RTF to Plain Text (C# Programming Guide)</span></span>
<span data-ttu-id="0085b-103">Формат документов RTF (Rich Text Format) был разработан корпорацией Майкрософт в конце 1980-х годов для эффективного обмена документами между различными операционными системами.</span><span class="sxs-lookup"><span data-stu-id="0085b-103">Rich Text Format (RTF) is a document format developed by Microsoft in the late 1980s to enable the exchange of documents across operating systems.</span></span> <span data-ttu-id="0085b-104">С документами в формате RTF можно работать в таких текстовых редакторах, как Microsoft Word и WordPad.</span><span class="sxs-lookup"><span data-stu-id="0085b-104">Both Microsoft Word and WordPad can read and write RTF documents.</span></span> <span data-ttu-id="0085b-105">На платформе .NET Framework предусмотрен элемент управления <xref:System.Windows.Forms.RichTextBox>, с помощью которого можно создать текстовый редактор, поддерживающий формат RTF и позволяющий пользователям работать с текстом в режиме WYSIWIG.</span><span class="sxs-lookup"><span data-stu-id="0085b-105">In the .NET Framework, you can use the <xref:System.Windows.Forms.RichTextBox> control to create a word processor that supports RTF and enables a user to apply formatting to text in a WYSIWIG manner.</span></span>  
  
 <span data-ttu-id="0085b-106">С помощью элемента управления <xref:System.Windows.Forms.RichTextBox> также можно программными средствами удалить из документа коды форматирования RTF и преобразовать его в обычный текст.</span><span class="sxs-lookup"><span data-stu-id="0085b-106">You can also use the <xref:System.Windows.Forms.RichTextBox> control to programmatically remove the RTF formatting codes from a document and convert it to plain text.</span></span> <span data-ttu-id="0085b-107">Для выполнения такого рода операций не требуется встраивать элемент управления в форму Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0085b-107">You do not need to embed the control in a Windows Form to perform this kind of operation.</span></span>  
  
### <a name="to-use-the-richtextbox-control-in-a-project"></a><span data-ttu-id="0085b-108">Использование элемента управления RichTextBox в проекте</span><span class="sxs-lookup"><span data-stu-id="0085b-108">To use the RichTextBox control in a project</span></span>  
  
1.  <span data-ttu-id="0085b-109">Добавьте ссылку на библиотеку System.Windows.Forms.dll.</span><span class="sxs-lookup"><span data-stu-id="0085b-109">Add a reference to System.Windows.Forms.dll.</span></span>  
  
2.  <span data-ttu-id="0085b-110">Добавьте директиву using для пространства имен `System.Windows.Forms` (необязательно).</span><span class="sxs-lookup"><span data-stu-id="0085b-110">Add a using directive for the `System.Windows.Forms` namespace (optional).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0085b-111">Пример</span><span class="sxs-lookup"><span data-stu-id="0085b-111">Example</span></span>  
 <span data-ttu-id="0085b-112">В следующем примере образец RTF-файла преобразуется в обычный текст.</span><span class="sxs-lookup"><span data-stu-id="0085b-112">The following example converts a sample RTF file to plain text.</span></span> <span data-ttu-id="0085b-113">Этот файл содержит форматирование RTF (например, сведения о шрифтах), четыре символа Юникода и четыре символа из расширенного набора ASCII.</span><span class="sxs-lookup"><span data-stu-id="0085b-113">The file contains RTF formatting (such as font information), four Unicode characters, and four extended ASCII characters.</span></span> <span data-ttu-id="0085b-114">В этом примере кода файл открывается, его содержимое передается в элемент управления <xref:System.Windows.Forms.RichTextBox> в формате RTF и затем извлекается в виде текста, после чего содержимое отображается в виде текста в <xref:System.Windows.Forms.MessageBox> и выводится в текстовый файл в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="0085b-114">The example code opens the file, passes its content to a <xref:System.Windows.Forms.RichTextBox> as RTF, retrieves the content as text, displays the text in a <xref:System.Windows.Forms.MessageBox>, and outputs the text to a file in UTF-8 format.</span></span>  
  
 <span data-ttu-id="0085b-115">`MessageBox` и выходной файл будут содержать следующий текст:</span><span class="sxs-lookup"><span data-stu-id="0085b-115">The `MessageBox` and the output file contain the following text:</span></span>  
  
```  
The Greek word for "psyche" is spelled ψυχή. The Greek letters are encoded in Unicode.  
These characters are from the extended ASCII character set (Windows code page 1252):  âäӑå  
```  
  
 <span data-ttu-id="0085b-116">[!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0085b-116">[!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]</span></span>  
  
 <span data-ttu-id="0085b-117">Символы RTF кодируются в 8-разрядной кодировке.</span><span class="sxs-lookup"><span data-stu-id="0085b-117">RTF characters are encoded in eight bits.</span></span> <span data-ttu-id="0085b-118">Тем не менее пользователи могут указывать символы Юникода в дополнение к символам расширенного набора ASCII из заданных кодовых страниц.</span><span class="sxs-lookup"><span data-stu-id="0085b-118">However, users can specify Unicode characters in addition to extended ASCII characters from specified code pages.</span></span> <span data-ttu-id="0085b-119">Поскольку свойство <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> имеет тип [string](../../../csharp/language-reference/keywords/string.md), символы кодируются в кодировке Юникода UTF-16.</span><span class="sxs-lookup"><span data-stu-id="0085b-119">Because the <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> property is of type [string](../../../csharp/language-reference/keywords/string.md), the characters are encoded as Unicode UTF-16.</span></span> <span data-ttu-id="0085b-120">В выходных текстовых данных все символы из расширенного набора ASCII и символы Юникода из исходного документа RTF кодируются корректно.</span><span class="sxs-lookup"><span data-stu-id="0085b-120">Any extended ASCII characters and Unicode characters from the source RTF document are correctly encoded in the text output.</span></span>  
  
 <span data-ttu-id="0085b-121">Если для записи текста на диск используется метод <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName>, текст будет закодирован с использованием UTF-8 (без метки порядка байтов).</span><span class="sxs-lookup"><span data-stu-id="0085b-121">If you use the <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> method to write the text to disk, the text will be encoded as UTF-8 (without a Byte Order Mark).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0085b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0085b-122">See Also</span></span>  
 <span data-ttu-id="0085b-123"><xref:System.Windows.Forms.RichTextBox?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0085b-123"><xref:System.Windows.Forms.RichTextBox?displayProperty=fullName></span></span>   
 [<span data-ttu-id="0085b-124">Строки</span><span class="sxs-lookup"><span data-stu-id="0085b-124">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

