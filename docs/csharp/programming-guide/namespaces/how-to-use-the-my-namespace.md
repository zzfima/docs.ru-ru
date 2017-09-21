---
title: "Практическое руководство. Использование пространства имен \"My\" (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 56577ff61c3f637c8e5a0969ae75d65d24ddaef7
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a>Практическое руководство. Использование пространства имен "My" (Руководство по программированию на C#)
Пространство имен <xref:Microsoft.VisualBasic.MyServices> (`My` в Visual Basic) обеспечивает простой и интуитивно понятный доступ к ряду классов .NET Framework, позволяя создавать код, взаимодействующий с компьютером, приложением, параметрами, ресурсами и т. д. Пространство имен `MyServices` изначально разработано для Visual Basic, однако может применяться и в приложениях C#.  
  
 Дополнительные сведения об использовании пространства имен `MyServices` из Visual Basic см. в разделе [Разработка с использованием пространства имен My](../../../visual-basic/developing-apps/development-with-my/index.md).  
  
## <a name="adding-a-reference"></a>Добавление ссылки  
 Прежде чем использовать классы `MyServices` в решении, необходимо добавить ссылку на библиотеку Visual Basic.  
  
#### <a name="to-add-a-reference-to-the-visual-basic-library"></a>Добавление ссылки на библиотеку Visual Basic  
  
1.  В **обозревателе решений** щелкните правой кнопкой мыши узел **Ссылки** и выберите команду **Добавить ссылку**.  
  
2.  В диалоговом окне **Ссылки** прокрутите список вниз и выберите библиотеку Microsoft.VisualBasic.dll.  
  
     Также можно включить следующую строку в раздел `using` в начале программы.  
  
     [!code-cs[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_1.cs)]  
  
## <a name="example"></a>Пример  
 В этом примере вызываются различные статические методы, содержащиеся в пространстве имен `MyServices`. Чтобы скомпилировать этот код, необходимо добавить в проект ссылку на библиотеку Microsoft.VisualBasic.DLL.  
  
 [!code-cs[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_2.cs)]  
  
 Некоторые классы из пространства имен `MyServices` нельзя вызывать из приложения C#, как, например, несовместимый класс <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>. Конкретно в этом случае вместо него можно использовать статические методы из состава <xref:Microsoft.VisualBasic.FileIO.FileSystem> (также входит в библиотеку VisualBasic.dll). Например, ниже показано, как дублировать каталог с помощью одного из таких методов:  
  
 [!code-cs[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_3.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Пространства имен](../../../csharp/programming-guide/namespaces/index.md)   
 [Использование пространств имен](../../../csharp/programming-guide/namespaces/using-namespaces.md)

