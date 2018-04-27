### <a name="marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>Перегрузки Marshal.SizeOf и Marshal.PtrToStructure нарушают работу динамического кода

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.5.1 динамическая привязка к методам <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)> или <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)> (с помощью Windows PowerShell, IronPython или ключевого слова dynamic в C#) может привести к исключению <code>MethodInvocationExceptions</code>, так как были добавлены новые перегрузки этих методов, которые могут быть неоднозначными для обработчиков скриптов.|
|Предложение|Обновите скрипты для четкого указания используемой перегрузки. Обычно нужно явным образом привести параметры типа метода как <xref:System.Type>. Дополнительные сведения и возможные решения этой проблемы см. по [этой ссылке](https://support.microsoft.com/kb/2909958/).|
|Область|Дополнительный номер|
|Версия|4.5.1|
|Тип|Среда выполнения|

