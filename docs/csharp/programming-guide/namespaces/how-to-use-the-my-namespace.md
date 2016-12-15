---
title: "Практическое руководство. Использование пространства имен &quot;My&quot; (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# - язык, доступ к пространству имен My"
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Использование пространства имен &quot;My&quot; (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Пространство имен <xref:Microsoft.VisualBasic.MyServices> \(`My` в Visual Basic\) обеспечивает простой и понятный доступ к ряду классов .NET Framework, позволяя пользователю создавать код, взаимодействующий с компьютером, приложением, параметрами, ресурсами и т. д.  Хотя изначально пространство имен `MyServices` предназначалось для использования в Visual Basic, оно может использоваться в приложениях C\#.  
  
 Дополнительные сведения об использовании пространства имен `MyServices` из Visual Basic см. в разделе [Разработка с использованием My](../../../visual-basic/developing-apps/development-with-my/index.md).  
  
## Добавление ссылки  
 Перед использованием классов `MyServices` в своем решении, вы должны добавить ссылку на библиотеку Visual Basic.  
  
#### Чтобы добавить ссылку на библиотеку Visual Basic  
  
1.  В окне **Обозреватель решений** щелкните правой кнопкой мыши узел **Ссылки** и выберите команду **Добавить ссылку**.  
  
2.  При отображении диалогового окна **Ссылки** выполните в списке прокрутку вниз и выберите Microsoft.VisualBasic.dll.  
  
     Возможно, вы также захотите включить в раздел `using` в начале программы следующую строку.  
  
     [!code-cs[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_1.cs)]  
  
## Пример  
 В этом примере вызываются различные статические методы, содержащиеся в пространстве имен `MyServices`.  Чтобы компиляция этого кода была возможной, в проект необходимо добавить ссылку на Microsoft.VisualBasic.DLL.  
  
 [!code-cs[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_2.cs)]  
  
 Из приложения C\# можно вызывать не все классы в пространстве имен `MyServices`: например, класс <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> является несовместимым.  В таком случае вместо этого можно использовать статические методы, являющиеся частью <xref:Microsoft.VisualBasic.FileIO.FileSystem>, которые также содержатся в VisualBasic.dll.  Например, далее описано использование одного из таких методов для дублирования каталога:  
  
 [!code-cs[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_3.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Пространства имен](../../../csharp/programming-guide/namespaces/index.md)   
 [Использование пространств имен](../../../csharp/programming-guide/namespaces/using-namespaces.md)