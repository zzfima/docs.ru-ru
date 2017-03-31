---
title: "Чтение данных из реестра и запись в реестр (Visual Basic) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry, writing to
- registry, reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1f148b00181c6c6a152b2f08ab765e0a385a7c89
ms.lasthandoff: 03/13/2017

---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a>Чтение данных из реестра и запись в реестр (Visual Basic)
В этом разделе описываются задачи и приводятся основные разделы, связанные с реестром.  
  
 При программировании в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] можно получить доступ к реестру с помощью функций, предоставляемых [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], классов платформы .NET Framework для работы с реестром. Реестр содержит данные, исходящие как от операционной системы, так и от приложений, установленных на компьютере. Работа с реестром может привести к нарушению безопасности, допуская несанкционированный доступ к системным ресурсам или защищенной информации.  
  
## <a name="in-this-section"></a>Содержание  
 [Практическое руководство. Создание раздела реестра и задание его значения](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 Описывает использование методов `CreateSubKey` и `SetValue` объекта `My.Computer.Registry` для создания раздела реестра и присвоения ему значения.  
  
 [Практическое руководство. Чтение значения из раздела реестра](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 Описывает использование метода `GetValue` объекта `My.Computer.Registry` для чтения значения из раздела реестра.  
  
 [Практическое руководство. Удаление раздела реестра](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 Описывает использование метода `DeleteSubKey` свойства `My.Computer.Registry.CurrentUser` для удаления раздела реестра.  
  
 [Чтение реестра и запись в него с использованием пространства имен Microsoft.Win32](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 Описывает использование классов `Registry` и `RegistryKey` объекта [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] для доступа к реестру.  
  
 [Безопасность и реестр](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 Описывает вопросы безопасности, связанные с реестром.  
  
## <a name="related-sections"></a>Связанные разделы  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 Список и описание членов объекта `My.Computer.Registry`.  
  
 <xref:Microsoft.Win32.Registry>  
 Обзор класса `Registry` со ссылками на отдельные разделы и члены.
