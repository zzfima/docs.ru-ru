---
title: Маршалинг делегата как метода обратного вызова
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff875f2807a14493ab81a9e354b5c4dcdf3d5feb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a>Маршалинг делегата как метода обратного вызова
В этом примере показан способ передачи делегатов в неуправляемую функцию, ожидающую указатели на функции. Делегат — это класс, который может содержать ссылку на метод. Делегат эквивалентен типобезопасному указателю на функцию или функции обратного вызова.  
  
> [!NOTE]
>  При использовании делегата в вызове функции общеязыковая среда выполнения защищает делегат от сборщика мусора в течение этого вызова. Однако если неуправляемая функция сохраняет делегат для использования после завершения вызова, необходимо вручную запретить сбор мусора до того, как неуправляемая функция завершит обработку делегата. Дополнительные сведения см. в разделах [Пример HandleRef](https://msdn.microsoft.com/library/ab23b04e-1d53-4ec7-b27a-e892d9298959(v=vs.100)) и [Пример GCHandle](https://msdn.microsoft.com/library/6acce798-0385-4ded-a790-77da842c113f(v=vs.100)).  
  
 В примере обратного вызова используются следующие неуправляемые функции со своими первоначальными объявлениями:  
  
-   функция **TestCallBack**, экспортированная из PinvokeLib.dll;  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   функция **TestCallBack2**, экспортированная из PinvokeLib.dll.  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 [PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) — это пользовательская неуправляемая библиотека, содержащая реализацию вышеуказанных функций.  
  
 В этом примере класс `LibWrap` содержит управляемые прототипы методов `TestCallBack` и `TestCallBack2`. Оба метода передают делегат функции обратного вызова в качестве параметра. Сигнатура делегата должна соответствовать сигнатуре метода, на который ссылается делегат. Например, подписи делегатов для `FPtr` и `FPtr2` аналогичны методам `DoSomething` и `DoSomething2`.  
  
## <a name="declaring-prototypes"></a>Объявление прототипов  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## <a name="calling-functions"></a>Вызов функций  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## <a name="see-also"></a>См. также  
 [Различные примеры маршалинга](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))  
 [Типы данных вызовов неуправляемого кода](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))  
 [Создание прототипов в управляемом коде](creating-prototypes-in-managed-code.md)
