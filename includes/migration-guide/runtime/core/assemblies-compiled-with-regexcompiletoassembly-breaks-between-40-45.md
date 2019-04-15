---
ms.openlocfilehash: 69b25db88c7580787bbb47fb0902b6bb072f8dde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235946"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a>Сборки, скомпилированные с прерываниями Regex.CompileToAssembly между версиями 4.0 и 4.5

|   |   |
|---|---|
|Подробные сведения|Если сборка компилированных регулярных выражений создается с помощью .NET Framework 4.5, но предназначена для .NET Framework 4, попытка использовать одно из регулярных выражений в этой сборке в системе с .NET Framework 4 создает исключение.|
|Предложение|Чтобы обойти эту проблему, можно воспользоваться одним из следующих способов:<ul><li>создать сборку, содержащую регулярные выражения, с помощью .NET Framework 4;</li><li>использовать интерпретированное регулярное выражение.</li></ul>|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|
