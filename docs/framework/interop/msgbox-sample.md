---
title: "MsgBox Sample | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "marshaling, MsgBox sample"
  - "data marshaling, MsgBox sample"
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# MsgBox Sample
В этом примере показывается, как передавать строковые типы по значению в качестве параметров In и когда использовать поля <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> и <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>.  
  
 В примере MsgBox используются следующая неуправляемая функция, показанная со своим исходным объявлением.  
  
-   Функция **MessageBox**, экспортированная из User32.dll.  
  
    ```  
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 В данном примере класс `LibWrap` содержит управляемый прототип для каждой неуправляемой функции, вызываемой классом `MsgBoxSample`.  Для одной и той же неуправляемой функции методы управляемых прототипов `MsgBox`, `MsgBox2` и `MsgBox3` объявляются по\-разному  
  
 Объявление метода `MsgBox2` приводит к неверным результатам в поле сообщения, поскольку заданный тип символов \(ANSI\) не совпадает с входной точкой `MessageBoxW`, которая является именем функции Юникода.  Объявление для `MsgBox3` приводит к несоответствию полей **EntryPoint**, **CharSet** и **ExactSpelling**.  Вызов метода `MsgBox3` создает исключение.  Подробные сведения об именовании строк и маршалинге имен см. в разделе [Задание кодировки](../../../docs/framework/interop/specifying-a-character-set.md).  
  
## Объявление прототипов  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## Вызов функций  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## См. также  
 [Marshaling Strings](../../../docs/framework/interop/marshaling-strings.md)   
 [Platform Invoke Data Types](http://msdn.microsoft.com/ru-ru/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [Default Marshaling for Strings](../../../docs/framework/interop/default-marshaling-for-strings.md)   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Задание кодировки](../../../docs/framework/interop/specifying-a-character-set.md)