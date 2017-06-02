---
title: "Практическое руководство: Включение XML IntelliSense в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: af67d0ee-a4a6-4abf-9c07-5a8cfe80d111
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 84af19189fa3fc510c8d4f8e408cbb2a393d8b8f
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-enable-xml-intellisense-in-visual-basic"></a>Практическое руководство. Включение XML IntelliSense в Visual Basic
XML IntelliSense в Visual Basic предоставляет завершение слов для элементов, определенных в схеме XML. Включение XML IntelliSense в Visual Basic, выполните следующие действия.  
  
1.  Получите файл XML-схемы (XSD) или файлы для файлов XML, которые приложение будет считывать или записи.  
  
2.  Включите файлы схемы XML в проект.  
  
3.  Импортируйте целевое пространство имен или пространства имен в файл кода или проект. Целевое пространство имен определяется `targetNamespace` или `tns` атрибут XSD-схемы.  
  
     Чтобы импортировать целевое пространство имен, используйте `Imports` оператор, или добавьте пространство имен для всех файлов кода в проекте с помощью **ссылки** страницы в конструкторе проектов.  
  
 Дополнительные сведения о возможностях XML IntelliSense в Visual Basic см. в разделе [XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md). Дополнительные сведения об импорте пространства имен XML см. в разделе [оператор Imports (пространство имен XML)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) или [страница "ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
 ![ссылка на видео](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") для просмотра видеоверсии этого раздела, в разделе [видео: Включение XML IntelliSense в Visual Basic](http://go.microsoft.com/fwlink/?LinkId=102466). Связанные демонстрационные видеоролики см. в разделе [как мне Включение XML IntelliSense и пространства имен XML используйте?](http://go.microsoft.com/fwlink/?LinkId=143035).  
  
## <a name="enable-xml-intellisense-in-visual-basic"></a>Включение XML IntelliSense в Visual Basic  
 Если имеется файл XML, но нет файла XSD-схемы для него, в пакете обновления&1; можно создать файл схемы XSD с помощью XML для мастера схем. Можно также использовать вывода схемы в XML-редакторе Visual Studio.  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-the-xml-to-schema-wizard-requires-sp1"></a>Создание файла схемы XSD для XML-файла с помощью XML для мастера схем (требуется пакет обновлений&1;)  
  
1.  В проекте, щелкните **Добавление нового элемента** на **проекта** меню.  
  
2.  Выберите **Xml to Schema** шаблона элемента, либо от **данные** или **Общие элементы** категорий шаблонов.  
  
3.  Укажите имя файла для XSD-файла или файлов, которые будут храниться в производного набора схем и нажмите кнопку **добавить**.  
  
4.  В **определение XML набора схем из XML-документов** окна, добавьте один или несколько XML-документов для определения набора схем XML.  
  
    -   Чтобы добавить текстовые файлы, содержащие XML-документов с помощью проводника, щелкните **добавить из файла**.  
  
    -   Чтобы добавить XML-документ из HTTP-адреса, щелкните **добавить из Интернета**.  
  
    -   Чтобы скопировать или напечатать содержимое XML-документа в мастере, щелкните **ввод или вставка XML**.  
  
5.  После указания всех источников XML-документов из которых нужно получить набор схем XML, нажмите кнопку **ОК** для определения схем XML значение. Набор схем сохраняется в папку проекта в один или несколько файлов XSD. (Для каждого пространства имен XML в схеме создается файл.)  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-schema-inference-in-the-visual-studio-xml-editor"></a>Создание файла схемы XSD для XML-файла с помощью вывода схемы в XML-редакторе Visual Studio  
  
1.  Изменение XML-файла в конструкторе Visual Studio XML.  
  
2.  Когда курсор находится где-нибудь в XML-файле **XML** появится меню. Щелкните **Create Schema** на **XML** меню. XSD-файл создается из XSD-схемы из XML-файла.  
  
3.  Сохраните файл схемы XSD.  
  
    > [!NOTE]
    >  Разные XSD-схемы могут быть получены из нескольких XML-документов, которые предназначены для одной и той же схемы. Это может произойти, когда определенные элементы и атрибуты находятся в одном XML-файле, а не в другом, или элементы включены в другом порядке. Если вы изучите XSD-схемы для полноты и точности.  
  
#### <a name="to-include-an-xsd-schema-file"></a>Для включения файла схемы XSD  
  
-   По умолчанию не отображается XSD-файлов в проектах Visual Basic. Если XSD-файл уже имеется в папках для проекта, нажмите кнопку **Показать все файлы** кнопки в **обозревателе решений**. Найдите XSD-файл в **обозревателе решений**, щелкните правой кнопкой мыши файл и нажмите кнопку **включить файл в проект**.  
  
-   Если XSD-файл еще не входит в проект, в **обозревателе решений**, щелкните правой кнопкой мыши папку, в которой требуется сохранить XSD-файл, выберите пункт **добавить**и нажмите кнопку **существующий элемент**. Найдите XSD-файл и нажмите кнопку **добавить**.  
  
#### <a name="to-import-an-xml-namespace-in-a-code-file"></a>Чтобы импортировать пространство имен XML в файле кода  
  
1.  Определение целевого пространства имен из XSD-схемы.  
  
2.  Добавьте в начало файла с кодом `Imports` инструкции для целевого пространства имен XML, как показано в следующем примере.  
  
     [!code-vb[VbXMLSamples&#1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]  
  
     Чтобы импортировать пространство имен XML как пространство имен по умолчанию, то есть, пространство имен, которое применяется к XML-элементов и атрибутов, которые не имеют префикса пространства имен, добавьте `Imports` инструкции для конечного пространства имен XML по умолчанию. Не указывайте префикс пространства имен. Ниже приведен пример `Imports` инструкции.  
  
     [!code-vb[VbXmlSamples&#50;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]  
  
#### <a name="to-import-an-xml-namespace-for-all-files-in-a-project"></a>Чтобы импортировать пространство имен XML для всех файлов в проекте  
  
1.  Пространство имен XML, импортированные в файле кода применяется к только что файл кода. Чтобы импортировать пространство имен XML, который применяется ко всем файлам кода в проекте, откройте конструктор проектов, дважды щелкнув **Мой проект** в **обозревателе решений**.  
  
2.  На **ссылки** вкладке **импортированные пространства имен** введите конечное пространство имен XML в виде полного объявления пространства имен XML (например, `<xmlns: ns="http://sampleNamespace">`). Если целевое пространство имен XML не указывает префикс пространства имен, пространство имен будет пространство имен XML по умолчанию для проекта.  
  
3.  Щелкните **добавить пользовательский импорт**.  
  
## <a name="see-also"></a>См. также  
 [Оператор Imports (пространство имен XML)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Страница "Ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)   
 [XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)

