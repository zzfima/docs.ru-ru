---
title: Практическое руководство. Выполнение базовых операций со строками в .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET Framework], examples
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1206648c694c9f09a600e3c70f4aa27118b2d458
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44178056"
---
# <a name="how-to-perform-basic-string-manipulations-in-net"></a><span data-ttu-id="a939d-102">Практическое руководство. Выполнение базовых операций со строками в .NET</span><span class="sxs-lookup"><span data-stu-id="a939d-102">How to: Perform Basic String Manipulations in .NET</span></span>
<span data-ttu-id="a939d-103">В следующем примере некоторые методы, описанные в руководстве по [базовым операциям со строками](../../../docs/standard/base-types/basic-string-operations.md), используются для создания класса, который выполняет обработку строк так же, как это происходит в реальном приложении.</span><span class="sxs-lookup"><span data-stu-id="a939d-103">The following example uses some of the methods discussed in the [Basic String Operations](../../../docs/standard/base-types/basic-string-operations.md) topics to construct a class that performs string manipulations in a manner that might be found in a real-world application.</span></span> <span data-ttu-id="a939d-104">Класс `MailToData` хранит имя и адрес человека в отдельных свойствах и предоставляет способ объединения полей `City`, `State` и `Zip` в одну строку для отображения пользователю.</span><span class="sxs-lookup"><span data-stu-id="a939d-104">The `MailToData` class stores the name and address of an individual in separate properties and provides a way to combine the `City`, `State`, and `Zip` fields into a single string for display to the user.</span></span> <span data-ttu-id="a939d-105">Более того, данный класс позволяет пользователю вводить сведения о городе, области и почтовом индексе в одну строку. Приложение автоматически анализирует эту строку и вводит необходимые сведения в соответствующее свойство.</span><span class="sxs-lookup"><span data-stu-id="a939d-105">Furthermore, the class allows the user to enter the city, state, and ZIP Code information as a single string; the application automatically parses the single string and enters the proper information into the corresponding property.</span></span>  
  
 <span data-ttu-id="a939d-106">В этом упрощенном примере используется консольное приложение с интерфейсом командной строки.</span><span class="sxs-lookup"><span data-stu-id="a939d-106">For simplicity, this example uses a console application with a command-line interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a939d-107">Пример</span><span class="sxs-lookup"><span data-stu-id="a939d-107">Example</span></span>  
 [!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
 [!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]  
  
 <span data-ttu-id="a939d-108">При выполнении предыдущего кода пользователю предлагается ввести его имя и адрес.</span><span class="sxs-lookup"><span data-stu-id="a939d-108">When the preceding code is executed, the user is asked to enter his or her name and address.</span></span> <span data-ttu-id="a939d-109">Приложение размещает сведения в соответствующих свойствах и отображает их для пользователя, создавая одну строку, в которой представлены сведения о городе, области и почтовом индексе.</span><span class="sxs-lookup"><span data-stu-id="a939d-109">The application places the information in the appropriate properties and displays the information back to the user, creating a single string that displays the city, state, and ZIP Code information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a939d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a939d-110">See also</span></span>

- [<span data-ttu-id="a939d-111">Базовые операции со строками в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a939d-111">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
