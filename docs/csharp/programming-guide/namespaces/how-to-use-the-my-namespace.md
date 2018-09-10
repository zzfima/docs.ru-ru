---
title: Практическое руководство. Использование пространства имен "My" (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
ms.openlocfilehash: a8ec3a96534693142d37d26ac0c08eec9298b178
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526210"
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
  
     [!code-csharp[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_1.cs)]  
  
## <a name="example"></a>Пример  
 В этом примере вызываются различные статические методы, содержащиеся в пространстве имен `MyServices`. Чтобы скомпилировать этот код, необходимо добавить в проект ссылку на библиотеку Microsoft.VisualBasic.DLL.  
  
 [!code-csharp[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_2.cs)]  
  
 Некоторые классы из пространства имен `MyServices` нельзя вызывать из приложения C#, как, например, несовместимый класс <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>. Конкретно в этом случае вместо него можно использовать статические методы из состава <xref:Microsoft.VisualBasic.FileIO.FileSystem> (также входит в библиотеку VisualBasic.dll). Например, ниже показано, как дублировать каталог с помощью одного из таких методов:  
  
 [!code-csharp[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_3.cs)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Пространства имен](../../../csharp/programming-guide/namespaces/index.md)  
- [Использование пространств имен](../../../csharp/programming-guide/namespaces/using-namespaces.md)
