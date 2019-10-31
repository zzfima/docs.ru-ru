---
title: Практическое руководство. Создание сборок взаимодействия их библиотек типов
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
ms.openlocfilehash: 7cca21630bd1dbd6896f882d058f288f603e95df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123895"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a><span data-ttu-id="b85c6-102">Практическое руководство. Создание сборок взаимодействия их библиотек типов</span><span class="sxs-lookup"><span data-stu-id="b85c6-102">How to: Generate Interop Assemblies from Type Libraries</span></span>
<span data-ttu-id="b85c6-103">[Программа импорта библиотек типов (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) — это средство командной строки, которое преобразует коклассы и интерфейсы, содержащиеся в библиотеке типов COM, в метаданные.</span><span class="sxs-lookup"><span data-stu-id="b85c6-103">The [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) is a command-line tool that converts the coclasses and interfaces contained in a COM type library to metadata.</span></span> <span data-ttu-id="b85c6-104">Это средство автоматически создает сборку взаимодействия и пространство имен для сведений о типе.</span><span class="sxs-lookup"><span data-stu-id="b85c6-104">This tool creates an interop assembly and namespace for the type information automatically.</span></span> <span data-ttu-id="b85c6-105">После того как метаданные класса стали доступными, управляемые клиенты могут создавать экземпляры типа COM и вызывать его методы, как если бы это был экземпляр .NET.</span><span class="sxs-lookup"><span data-stu-id="b85c6-105">After the metadata of a class is available, managed clients can create instances of the COM type and call its methods, just as if it were a .NET instance.</span></span> <span data-ttu-id="b85c6-106">Средство Tlbimp.exe преобразует всю библиотеку типов в метаданные за один раз и не может создать сведения о типах для подмножества типов, определенных в библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="b85c6-106">Tlbimp.exe converts an entire type library to metadata at once and cannot generate type information for a subset of the types defined in a type library.</span></span>  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a><span data-ttu-id="b85c6-107">Создание сборки взаимодействия из библиотеки типов</span><span class="sxs-lookup"><span data-stu-id="b85c6-107">To generate an interop assembly from a type library</span></span>  
  
1. <span data-ttu-id="b85c6-108">Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b85c6-108">Use the following command:</span></span>  
  
     <span data-ttu-id="b85c6-109">**tlbimp** \<*файл_библиотеки_типов*></span><span class="sxs-lookup"><span data-stu-id="b85c6-109">**tlbimp** \<*type-library-file*></span></span>  
  
     <span data-ttu-id="b85c6-110">При указании параметра **/out:** создается сборка взаимодействия с измененным именем, например LOANLib.dll.</span><span class="sxs-lookup"><span data-stu-id="b85c6-110">Adding the **/out:** switch produces an interop assembly with an altered name, such as LOANLib.dll.</span></span> <span data-ttu-id="b85c6-111">Изменение имени сборки взаимодействия помогает отличить эту сборку от исходного файла DLL COM и избежать возможных проблем с повторяющимися именами.</span><span class="sxs-lookup"><span data-stu-id="b85c6-111">Altering the interop assembly name can help distinguish it from the original COM DLL and prevent problems that can occur from having duplicate names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b85c6-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b85c6-112">Example</span></span>  
 <span data-ttu-id="b85c6-113">Следующая команда создает сборку Loanlib.dll в пространстве имен `Loanlib`.</span><span class="sxs-lookup"><span data-stu-id="b85c6-113">The following command produces the Loanlib.dll assembly in the `Loanlib` namespace.</span></span>  
  
```  
tlbimp Loanlib.tlb  
```  
  
 <span data-ttu-id="b85c6-114">Следующая команда создает сборку взаимодействия с измененным именем (LOANLib.dll).</span><span class="sxs-lookup"><span data-stu-id="b85c6-114">The following command produces an interop assembly with an altered name (LOANLib.dll).</span></span>  
  
```  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="b85c6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b85c6-115">See also</span></span>

- [<span data-ttu-id="b85c6-116">Импорт библиотеки типов в виде сборки</span><span class="sxs-lookup"><span data-stu-id="b85c6-116">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="b85c6-117">Предоставление COM-компонентов платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b85c6-117">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
