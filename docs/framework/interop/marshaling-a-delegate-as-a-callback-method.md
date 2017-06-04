---
title: "Marshaling a Delegate as a Callback Method | Microsoft Docs"
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
  - "data marshaling, Callback sample"
  - "marshaling, Callback sample"
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Marshaling a Delegate as a Callback Method
В этом примере показан способ передачи делегатов в неуправляемую функцию, ожидающую указатели функции.  Делегат является классом, который может содержать ссылку на метод и эквивалентен типобезопасному указателю функции или функции обратного вызова.  
  
> [!NOTE]
>  При использовании делегата в вызове, среда CLR защищает делегат от процесса сбора мусора на протяжении всего вызова.  Но если неуправляемая функция сохраняет делегат для использования после завершения вызова, необходимо предотвратить сборку мусора вручную до тех пор, пока неуправляемая функция не закончит работу с делегатом.  Дополнительные сведения см. в разделах [Пример HandleRef](http://msdn.microsoft.com/ru-ru/ab23b04e-1d53-4ec7-b27a-e892d9298959) и [Пример GCHandle](http://msdn.microsoft.com/ru-ru/6acce798-0385-4ded-a790-77da842c113f).  
  
 В примере Callback используются следующие неуправляемые функции, показанные со своим исходным объявлением.  
  
-   Функция **TestCallBack**, экспортированная из PinvokeLib.dll.  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   **TestCallBack2**, экспортированная из PinvokeLib.dll.  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 [PinvokeLib.dll](http://msdn.microsoft.com/ru-ru/5d1438d7-9946-489d-8ede-6c694a08f614) — это настраиваемая неуправляемая библиотека, содержащая реализацию ранее описанных функций.  
  
 В этом примере класс `LibWrap` содержит управляемые прототипы для методов `TestCallBack` и `TestCallBack2`.  Оба метода передают делегат в виде параметра в функцию обратного вызова.  Сигнатура делегата должна соответствовать сигнатуре метода, на который он ссылается.  Например, делегаты `FPtr` и `FPtr2` имеют сигнатуры, идентичные методам `DoSomething` и `DoSomething2`.  
  
## Объявление прототипов  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## Вызов функций  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## См. также  
 [Miscellaneous Marshaling Samples](http://msdn.microsoft.com/ru-ru/a915c948-54e9-4d0f-a525-95a77fd8ed70)   
 [Platform Invoke Data Types](http://msdn.microsoft.com/ru-ru/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)