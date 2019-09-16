---
title: Пример MsgBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71d7bb4cc85b0388e18cc7304dfa8c7951eab629
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894161"
---
# <a name="msgbox-sample"></a>Пример MsgBox
В этом примере демонстрируется, как передавать строковые типы по значению в качестве параметров ввода и когда следует использовать поля <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> и <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>.  
  
 В примере используются следующие неуправляемые функции, показанные с исходными объявлениями:  
  
- **MessageBox** экспортируется из User32.dll.  
  
    ```cpp
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 В этом примере класс `LibWrap` содержит управляемый прототип для каждой неуправляемой функции, вызываемой классом `MsgBoxSample`. Управляемые прототипы методов `MsgBox`, `MsgBox2` и `MsgBox3` содержат разные объявления для одной и той же неуправляемой функции.  
  
 Объявление `MsgBox2` приводит к выводу некорректных данных в окне сообщения, поскольку символьный тип, указанный как ANSI, не соответствует точке входа `MessageBoxW`, которая определяет функцию Юникода. Объявление `MsgBox3` приводит к несоответствию между полями **EntryPoint**, **CharSet** и **ExactSpelling**. При вызове `MsgBox3` возникает исключение. Дополнительные сведения об именовании строк и маршалинге имен см. в разделе [Определение кодировки](specifying-a-character-set.md).  
  
## <a name="declaring-prototypes"></a>Объявление прототипов  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a>Вызов функций  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a>См. также

- [Mаршалинг строк](marshaling-strings.md)
- [Маршалинг по умолчанию для строк](default-marshaling-for-strings.md)
- [Создание прототипов в управляемом коде](creating-prototypes-in-managed-code.md)
- [Определение кодировки](specifying-a-character-set.md)
