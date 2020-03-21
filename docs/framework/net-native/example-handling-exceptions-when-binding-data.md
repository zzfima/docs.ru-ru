---
title: 'Пример: Обработка исключений при привязке данных'
ms.date: 03/30/2017
ms.assetid: bd63ed96-9853-46dc-ade5-7bd1b0f39110
ms.openlocfilehash: b774d1bce4f4d1c03258ed44b27d3871e7c5275f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181019"
---
# <a name="example-handling-exceptions-when-binding-data"></a>Пример: Обработка исключений при привязке данных
> [!NOTE]
> В этом разделе рассматривается предварительная версия программного обеспечения для разработчиков машинного кода .NET. Предварительную версию можно скачать на [веб-сайте Microsoft Connect](https://go.microsoft.com/fwlink/?LinkId=394611) (требуется регистрация).  
  
 В следующем примере показано, как разрешить исключение [MissingMetadataException,](missingmetadataexception-class-net-native.md) которое выбрасывается при попытке приложения, компиляции с помощью цепочки инструментов .NET Native, связать данные. Сведения об исключении:  
  
```output
This operation cannot be carried out as metadata for the following type was removed for performance reasons:
App.ViewModels.MainPageVM  
```  
  
 Ниже приведен связанный стек вызова:  
  
```output
Reflection::Execution::ReflectionDomainSetupImplementation.CreateNonInvokabilityException+0x238  
Reflection::Core::ReflectionDomain.CreateNonInvokabilityException+0x2e  
Reflection::Core::Execution::ExecutionEnvironment.+0x316  
System::Reflection::Runtime::PropertyInfos::RuntimePropertyInfo.GetValue+0x1cb  
System::Reflection::PropertyInfo.GetValue+0x22  
System::Runtime::InteropServices::WindowsRuntime::CustomPropertyImpl.GetValue+0x42  
App!$66_Interop::McgNative.Func_IInspectable_IInspectable+0x158  
App!$66_Interop::McgNative::__vtable_Windows_UI_Xaml_Data__ICustomProperty.GetValue__STUB+0x46  
Windows_UI_Xaml!DirectUI::PropertyProviderPropertyAccess::GetValue+0x3f
Windows_UI_Xaml!DirectUI::PropertyAccessPathStep::GetValue+0x31
Windows_UI_Xaml!DirectUI::PropertyPathListener::ConnectPathStep+0x113  
```  
  
## <a name="what-was-the-app-doing"></a>Что делало это приложение?  
 В основе стека кадры из <xref:Windows.UI.Xaml?displayProperty=nameWithType> пространства имен указывают на то, что работал движок визуализации XAML.   Использование метода <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType>указывает на поиск на основе отражения значения свойства типа, метаданные которого были удалены.  
  
 На первом шаге предоставления директивы метаданных следовало бы добавить метаданные `serialize` для типа, чтобы его свойства стали доступны:  
  
```xml  
<Type Name="App.ViewModels.MainPageVM" Serialize="Required Public" />  
```  
  
## <a name="is-this-an-isolated-case"></a>Это изолированный случай?  
 В этом сценарии, если привязка данных имеет неполные метаданные для одной модели `ViewModel`, это может быть справедливо и для других.  Если код структурирован таким образом, что все модели просмотра приложения находятся в пространстве имен `App.ViewModels`, можно использовать более общую директиву среды выполнения:  
  
```xml  
<Namespace Name="App.ViewModels " Serialize="Required Public" />  
```  
  
## <a name="could-the-code-be-rewritten-to-not-use-reflection"></a>Можно переписать код, чтобы не использовать отражение?  
 Так как привязки данных интенсивно использует отражение, изменение кода, чтобы избежать отражения невозможно.  
  
 Однако, существуют способы задания `ViewModel` странице XAML таким образом, чтобы цепочка инструментов могла связать привязки свойства с нужным типом во время компиляции и сохранить метаданные без использования директивы среды выполнения.  Например, можно применить <xref:Windows.UI.Xaml.Data.BindableAttribute?displayProperty=nameWithType> атрибут к свойствам. Это вынуждает компилятор XAML создать необходимые таблицы подстановок и избежать использования директивы среды выполнения в файле Default.rd.xml.  
  
## <a name="see-also"></a>См. также раздел

- [Начало работы](getting-started-with-net-native.md)
- [Пример: Устранение неполадок динамического программирования](example-troubleshooting-dynamic-programming.md)
