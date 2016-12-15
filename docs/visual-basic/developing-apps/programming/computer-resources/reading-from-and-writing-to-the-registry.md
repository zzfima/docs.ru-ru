---
title: "Чтение данных из реестра и запись в реестр (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Computer.Registry - объект, задачи"
  - "реестр, чтение"
  - "реестр, запись в"
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Чтение данных из реестра и запись в реестр (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Этот раздел описывает задачу и на концептуальные разделы, связанных с реестром.  
  
 При программировании в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] можно получить доступ к реестру с помощью функций, предоставляемых [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], или классов платформы .NET Framework для работы с реестром.  Реестр содержит данные, исходящие как от операционной системы, так и от приложений, установленных на компьютере.  Работа с реестром может привести к нарушению безопасности, допуская несанкционированный доступ к системным ресурсам или защищенной информации.  
  
## В этом подразделе  
 [Практическое руководство. Создание раздела реестра и задание его значения](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 Описывает использование `CreateSubKey` и  `SetValue` методы   `My.Computer.Registry` объект для создания раздела реестра и установить его значение.  
  
 [Практическое руководство. Чтение значения из раздела реестра](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 Описывает использование `GetValue` метод   `My.Computer.Registry` объект, для которого чтение значения из раздела реестра.  
  
 [Практическое руководство. Удаление раздела реестра](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 Описывает использование `DeleteSubKey` метод   `My.Computer.Registry.CurrentUser` свойство для удаления раздела реестра.  
  
 [Чтение реестра и запись в него с использованием пространства имен Microsoft.Win32](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 Описывает использование `Registry` и  `RegistryKey` классы   [!INCLUDE[.net framework]()] получить доступ к реестру.  
  
 [Безопасность и реестр](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 Обсуждение вопросов безопасности, связанных с реестром.  
  
## Связанные подразделы  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 Список и описание членов объекта `My.Computer.Registry`.  
  
 <xref:Microsoft.Win32.Registry>  
 Обзор класса `Registry` со ссылками на отдельные разделы и члены.