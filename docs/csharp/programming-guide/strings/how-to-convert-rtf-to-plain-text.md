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
# <a name="how-to-convert-rtf-to-plain-text-c-programming-guide"></a>Практическое руководство. Преобразование формата RTF в обычный текст (Руководство по программированию в C#)
Формат документов RTF (Rich Text Format) был разработан корпорацией Майкрософт в конце 1980-х годов для эффективного обмена документами между различными операционными системами. С документами в формате RTF можно работать в таких текстовых редакторах, как Microsoft Word и WordPad. На платформе .NET Framework предусмотрен элемент управления <xref:System.Windows.Forms.RichTextBox>, с помощью которого можно создать текстовый редактор, поддерживающий формат RTF и позволяющий пользователям работать с текстом в режиме WYSIWIG.  
  
 С помощью элемента управления <xref:System.Windows.Forms.RichTextBox> также можно программными средствами удалить из документа коды форматирования RTF и преобразовать его в обычный текст. Для выполнения такого рода операций не требуется встраивать элемент управления в форму Windows Forms.  
  
### <a name="to-use-the-richtextbox-control-in-a-project"></a>Использование элемента управления RichTextBox в проекте  
  
1.  Добавьте ссылку на библиотеку System.Windows.Forms.dll.  
  
2.  Добавьте директиву using для пространства имен `System.Windows.Forms` (необязательно).  
  
## <a name="example"></a>Пример  
 В следующем примере образец RTF-файла преобразуется в обычный текст. Этот файл содержит форматирование RTF (например, сведения о шрифтах), четыре символа Юникода и четыре символа из расширенного набора ASCII. В этом примере кода файл открывается, его содержимое передается в элемент управления <xref:System.Windows.Forms.RichTextBox> в формате RTF и затем извлекается в виде текста, после чего содержимое отображается в виде текста в <xref:System.Windows.Forms.MessageBox> и выводится в текстовый файл в формате UTF-8.  
  
 `MessageBox` и выходной файл будут содержать следующий текст:  
  
```  
The Greek word for "psyche" is spelled ψυχή. The Greek letters are encoded in Unicode.  
These characters are from the extended ASCII character set (Windows code page 1252):  âäӑå  
```  
  
 [!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]  
  
 Символы RTF кодируются в 8-разрядной кодировке. Тем не менее пользователи могут указывать символы Юникода в дополнение к символам расширенного набора ASCII из заданных кодовых страниц. Поскольку свойство <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> имеет тип [string](../../../csharp/language-reference/keywords/string.md), символы кодируются в кодировке Юникода UTF-16. В выходных текстовых данных все символы из расширенного набора ASCII и символы Юникода из исходного документа RTF кодируются корректно.  
  
 Если для записи текста на диск используется метод <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName>, текст будет закодирован с использованием UTF-8 (без метки порядка байтов).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.RichTextBox?displayProperty=fullName>   
 [Строки](../../../csharp/programming-guide/strings/index.md)

