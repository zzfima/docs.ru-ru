---
title: Настройка атрибутов сборки
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- assembly binding, attributes
- assembly manifest, attributes
ms.assetid: 36a98a81-b5b5-4c19-912a-11f91eff7f4e
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 0e4e2e595ed4f95511bd23ab0ed00139f71b2c8b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740470"
---
# <a name="set-assembly-attributes"></a>Настройка атрибутов сборки

Атрибуты сборки — это значения, которые предоставляют сведения о сборке. Атрибуты разделяются на следующие группы.

- Атрибуты удостоверения сборки

- Информационные атрибуты

- Атрибуты манифеста сборки

- Атрибуты строгого имени

## <a name="assembly-identity-attributes"></a>Атрибуты удостоверения сборки

Три атрибута вместе со строгим именем (если оно применимо) определяют удостоверение сборки: имя, версия, язык и региональные параметры. Эти атрибуты формируют полное имя сборки и являются обязательными при ссылке на сборку в коде. Атрибуты можно использовать для задания версии сборки и языка и региональных параметров. Компилятор или [компоновщик сборок (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) задает значение имени при создании сборки на основе файла, содержащего манифест сборки.

В следующей таблице описаны атрибуты версии и языка и региональных параметров.

|Атрибут удостоверения сборки|ОПИСАНИЕ|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyCultureAttribute>|Перечислимое поле, указывающее язык и региональные параметры, поддерживаемые сборкой. В сборке можно также указать независимость от языка и региональных параметров, чтобы указать, что сборка содержит ресурсы для языка и региональных параметров по умолчанию. **Примечание.**  Среда выполнения рассматривает любую сборку, у которой для атрибута языка и региональных параметров не задано значение NULL, в качестве вспомогательной сборки. Такие сборки подчиняются правилам привязки вспомогательных сборок. Дополнительные сведения см. в разделе [Обнаружение сборок в среде выполнения](../../framework/deployment/how-the-runtime-locates-assemblies.md).|
|<xref:System.Reflection.AssemblyFlagsAttribute>|Значение, задающее атрибуты сборки: например, может ли сборка выполняться параллельно.|
|<xref:System.Reflection.AssemblyVersionAttribute>|Числовое значение в формате *основной_номер*.*дополнительный_номер*.*номер_сборки*.*номер_редакции* (например, 2.4.0.0). Среда CLR использует это значение для выполнения операций привязки в сборках со строгими именами. **Примечание.**  Если атрибут <xref:System.Reflection.AssemblyInformationalVersionAttribute> не применен к сборке, то номер версии, задаваемый атрибутом <xref:System.Reflection.AssemblyVersionAttribute>, используется свойствами <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> и <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType>.|

В следующем примере кода показано, как применить атрибуты версии и языка и региональных параметров сборки.

```cpp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")];
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")];
```

```csharp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")]
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")]
```

```vb
' Set version number for the assembly.
<Assembly:AssemblyVersionAttribute("4.3.2.1")>
' Set culture as German.
<Assembly:AssemblyCultureAttribute("de")>
```

## <a name="informational-attributes"></a>Информационные атрибуты

Информационные атрибуты можно использовать для предоставления дополнительных сведений о компании или продукте в сборке. В следующей таблице описаны информационные атрибуты, которые можно применить к сборке.

|Информационный атрибут|ОПИСАНИЕ|
|-----------------------------|-----------------|
|<xref:System.Reflection.AssemblyCompanyAttribute>|Строковое значение, содержащее название компании.|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|Строковое значение, содержащее сведения об авторских правах.|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Строковое значение, содержащее номер версии файла Win32. Обычно по умолчанию здесь используется версия сборки.|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|Строковое значение, содержащее сведения о версии, которые не используются средой CLR, например полный номер версии продукта. **Примечание.**  Если этот атрибут применен к сборке, указываемую им строку можно получить во время выполнения с помощью свойства <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>. Эта строка также используется в пути и разделе реестра, предоставляемых свойствами <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> и <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType>.|
|<xref:System.Reflection.AssemblyProductAttribute>|Строковое значение, содержащее сведения о продукте.|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|Строковое значение, содержащее сведения о товарном знаке.|

Эти атрибуты могут отображаться на странице свойств сборки в Windows и могут быть переопределены с помощью параметра компилятора **/win32res** , с помощью которого вы можете задать собственный файл ресурсов Win32.

## <a name="assembly-manifest-attributes"></a>Атрибуты манифеста сборки

Атрибуты манифеста сборки можно использовать для предоставления сведений в манифесте сборки, включая название, описание, псевдоним по умолчанию и конфигурацию. В следующей таблице описаны атрибуты манифеста сборки.

|Атрибуты манифеста сборки|ОПИСАНИЕ|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Строковое значение, содержащее конфигурацию сборки, например Retail или Debug. Среда выполнения не использует это значение.|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Строковое значение, содержащее псевдоним по умолчанию, используемый для ссылки на эту сборку из других сборок. Это значение предоставляет понятное имя, если имя сборки само по себе не является понятным (например, если это значение идентификатора GUID). Это значение можно также использовать как краткую форму полного имени сборки.|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Строковое значение, содержащее краткое описание сути и назначения сборки.|
|<xref:System.Reflection.AssemblyTitleAttribute>|Строковое значение, содержащее понятное имя сборки. Например, сборка с именем *comdlg* может иметь название "Элемент управления стандартного диалогового окна Майкрософт".|

## <a name="strong-name-attributes"></a>Атрибуты строгого имени

Атрибуты строгого имени можно использовать для задания строгого имени сборки. В таблице ниже описываются атрибуты строгого имени.

|Атрибут строгого имени|ОПИСАНИЕ|
|----------------------------|-----------------|
|<xref:System.Reflection.AssemblyDelaySignAttribute>|Логическое значение, указывающее, что используется отложенная подпись.|
|<xref:System.Reflection.AssemblyKeyFileAttribute>|Строковое значение, указывающее имя файла, который содержит открытый ключ (при использовании отложенной подписи), или открытый и закрытый ключи, передаваемые в качестве параметра в конструктор этого атрибута. Обратите внимание, что имя файла указано относительно пути к выходному файлу (*EXE* или *DLL*), а не пути к исходному файлу.|
|<xref:System.Reflection.AssemblyKeyNameAttribute>|Указывает контейнер ключей, содержащий пару ключей, передаваемых в качестве параметра в конструктор этого атрибута.|

В следующем примере кода показаны атрибуты, применяемые при использовании отложенной подписи для создания сборки со строгим именем с помощью файла открытого ключа *myKey.snk*.

```cpp
[assembly:AssemblyKeyFileAttribute("myKey.snk")];
[assembly:AssemblyDelaySignAttribute(true)];
```

```csharp
[assembly:AssemblyKeyFileAttribute("myKey.snk")]
[assembly:AssemblyDelaySignAttribute(true)]
```

```vb
<Assembly:AssemblyKeyFileAttribute("myKey.snk")>
<Assembly:AssemblyDelaySignAttribute(True)>
```

## <a name="see-also"></a>См. также

- [Создание сборок](create.md)
