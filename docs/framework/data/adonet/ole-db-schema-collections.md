---
title: Коллекции схемы OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f1cb5e1fe967088b44fa4045dfe50c1c57d963eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="df877-102">Коллекции схемы OLE DB</span><span class="sxs-lookup"><span data-stu-id="df877-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="df877-103">В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="df877-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="df877-104">Поставщик OLE DB для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="df877-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="df877-105">Драйвер Microsoft SQL Server OLE DB поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем:</span><span class="sxs-lookup"><span data-stu-id="df877-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="df877-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="df877-106">Tables</span></span>  
  
-   <span data-ttu-id="df877-107">Столбцы</span><span class="sxs-lookup"><span data-stu-id="df877-107">Columns</span></span>  
  
-   <span data-ttu-id="df877-108">Процедуры</span><span class="sxs-lookup"><span data-stu-id="df877-108">Procedures</span></span>  
  
-   <span data-ttu-id="df877-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="df877-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="df877-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="df877-110">Catalog</span></span>  
  
-   <span data-ttu-id="df877-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="df877-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="df877-112">Таблицы</span><span class="sxs-lookup"><span data-stu-id="df877-112">Tables</span></span>  
  
|<span data-ttu-id="df877-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-113">ColumnName</span></span>|<span data-ttu-id="df877-114">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-115">TABLE_CATALOG</span></span>|<span data-ttu-id="df877-116">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-116">String</span></span>|  
|<span data-ttu-id="df877-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="df877-118">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-118">String</span></span>|  
|<span data-ttu-id="df877-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-119">TABLE_NAME</span></span>|<span data-ttu-id="df877-120">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-120">String</span></span>|  
|<span data-ttu-id="df877-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-121">TABLE_TYPE</span></span>|<span data-ttu-id="df877-122">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-122">String</span></span>|  
|<span data-ttu-id="df877-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="df877-123">TABLE_GUID</span></span>|<span data-ttu-id="df877-124">Guid</span><span class="sxs-lookup"><span data-stu-id="df877-124">Guid</span></span>|  
|<span data-ttu-id="df877-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df877-125">DESCRIPTION</span></span>|<span data-ttu-id="df877-126">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-126">String</span></span>|  
|<span data-ttu-id="df877-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="df877-127">TABLE_PROPID</span></span>|<span data-ttu-id="df877-128">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-128">Int64</span></span>|  
|<span data-ttu-id="df877-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df877-129">DATE_CREATED</span></span>|<span data-ttu-id="df877-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-130">DateTime</span></span>|  
|<span data-ttu-id="df877-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df877-131">DATE_MODIFIED</span></span>|<span data-ttu-id="df877-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="df877-133">Столбцы</span><span class="sxs-lookup"><span data-stu-id="df877-133">Columns</span></span>  
  
|<span data-ttu-id="df877-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-134">ColumnName</span></span>|<span data-ttu-id="df877-135">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-136">TABLE_CATALOG</span></span>|<span data-ttu-id="df877-137">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-137">String</span></span>|  
|<span data-ttu-id="df877-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="df877-139">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-139">String</span></span>|  
|<span data-ttu-id="df877-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-140">TABLE_NAME</span></span>|<span data-ttu-id="df877-141">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-141">String</span></span>|  
|<span data-ttu-id="df877-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-142">COLUMN_NAME</span></span>|<span data-ttu-id="df877-143">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-143">String</span></span>|  
|<span data-ttu-id="df877-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="df877-144">COLUMN_GUID</span></span>|<span data-ttu-id="df877-145">Guid</span><span class="sxs-lookup"><span data-stu-id="df877-145">Guid</span></span>|  
|<span data-ttu-id="df877-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="df877-146">COLUMN_PROPID</span></span>|<span data-ttu-id="df877-147">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-147">Int64</span></span>|  
|<span data-ttu-id="df877-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df877-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="df877-149">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-149">Int64</span></span>|  
|<span data-ttu-id="df877-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="df877-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="df877-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-151">Boolean</span></span>|  
|<span data-ttu-id="df877-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="df877-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="df877-153">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-153">String</span></span>|  
|<span data-ttu-id="df877-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="df877-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="df877-155">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-155">Int64</span></span>|  
|<span data-ttu-id="df877-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="df877-156">IS_NULLABLE</span></span>|<span data-ttu-id="df877-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-157">Boolean</span></span>|  
|<span data-ttu-id="df877-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-158">DATA_TYPE</span></span>|<span data-ttu-id="df877-159">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-159">Int32</span></span>|  
|<span data-ttu-id="df877-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="df877-160">TYPE_GUID</span></span>|<span data-ttu-id="df877-161">Guid</span><span class="sxs-lookup"><span data-stu-id="df877-161">Guid</span></span>|  
|<span data-ttu-id="df877-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df877-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="df877-163">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-163">Int64</span></span>|  
|<span data-ttu-id="df877-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df877-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="df877-165">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-165">Int64</span></span>|  
|<span data-ttu-id="df877-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df877-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="df877-167">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-167">Int32</span></span>|  
|<span data-ttu-id="df877-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="df877-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="df877-169">Int16</span><span class="sxs-lookup"><span data-stu-id="df877-169">Int16</span></span>|  
|<span data-ttu-id="df877-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df877-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="df877-171">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-171">Int64</span></span>|  
|<span data-ttu-id="df877-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="df877-173">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-173">String</span></span>|  
|<span data-ttu-id="df877-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="df877-175">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-175">String</span></span>|  
|<span data-ttu-id="df877-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="df877-177">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-177">String</span></span>|  
|<span data-ttu-id="df877-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="df877-179">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-179">String</span></span>|  
|<span data-ttu-id="df877-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="df877-181">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-181">String</span></span>|  
|<span data-ttu-id="df877-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-182">COLLATION_NAME</span></span>|<span data-ttu-id="df877-183">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-183">String</span></span>|  
|<span data-ttu-id="df877-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="df877-185">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-185">String</span></span>|  
|<span data-ttu-id="df877-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="df877-187">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-187">String</span></span>|  
|<span data-ttu-id="df877-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-188">DOMAIN_NAME</span></span>|<span data-ttu-id="df877-189">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-189">String</span></span>|  
|<span data-ttu-id="df877-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df877-190">DESCRIPTION</span></span>|<span data-ttu-id="df877-191">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-191">String</span></span>|  
|<span data-ttu-id="df877-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="df877-192">COLUMN_LCID</span></span>|<span data-ttu-id="df877-193">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-193">Int32</span></span>|  
|<span data-ttu-id="df877-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="df877-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="df877-195">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-195">Int32</span></span>|  
|<span data-ttu-id="df877-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="df877-196">COLUMN_SORTID</span></span>|<span data-ttu-id="df877-197">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-197">Int32</span></span>|  
|<span data-ttu-id="df877-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="df877-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="df877-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="df877-199">Byte[]</span></span>|  
|<span data-ttu-id="df877-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="df877-200">IS_COMPUTED</span></span>|<span data-ttu-id="df877-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="df877-202">Процедуры</span><span class="sxs-lookup"><span data-stu-id="df877-202">Procedures</span></span>  
  
|<span data-ttu-id="df877-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-203">ColumnName</span></span>|<span data-ttu-id="df877-204">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="df877-206">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-206">String</span></span>|  
|<span data-ttu-id="df877-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="df877-208">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-208">String</span></span>|  
|<span data-ttu-id="df877-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="df877-210">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-210">String</span></span>|  
|<span data-ttu-id="df877-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="df877-212">Int16</span><span class="sxs-lookup"><span data-stu-id="df877-212">Int16</span></span>|  
|<span data-ttu-id="df877-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="df877-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="df877-214">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-214">String</span></span>|  
|<span data-ttu-id="df877-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df877-215">DESCRIPTION</span></span>|<span data-ttu-id="df877-216">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-216">String</span></span>|  
|<span data-ttu-id="df877-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df877-217">DATE_CREATED</span></span>|<span data-ttu-id="df877-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-218">DateTime</span></span>|  
|<span data-ttu-id="df877-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df877-219">DATE_MODIFIED</span></span>|<span data-ttu-id="df877-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="df877-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="df877-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="df877-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-222">ColumnName</span></span>|<span data-ttu-id="df877-223">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="df877-225">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-225">String</span></span>|  
|<span data-ttu-id="df877-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="df877-227">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-227">String</span></span>|  
|<span data-ttu-id="df877-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="df877-229">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-229">String</span></span>|  
|<span data-ttu-id="df877-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-230">PARAMETER_NAME</span></span>|<span data-ttu-id="df877-231">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-231">String</span></span>|  
|<span data-ttu-id="df877-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df877-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="df877-233">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-233">Int32</span></span>|  
|<span data-ttu-id="df877-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="df877-235">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-235">Int32</span></span>|  
|<span data-ttu-id="df877-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="df877-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="df877-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-237">Boolean</span></span>|  
|<span data-ttu-id="df877-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="df877-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="df877-239">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-239">String</span></span>|  
|<span data-ttu-id="df877-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="df877-240">IS_NULLABLE</span></span>|<span data-ttu-id="df877-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-241">Boolean</span></span>|  
|<span data-ttu-id="df877-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-242">DATA_TYPE</span></span>|<span data-ttu-id="df877-243">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-243">Int32</span></span>|  
|<span data-ttu-id="df877-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df877-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="df877-245">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-245">Int64</span></span>|  
|<span data-ttu-id="df877-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df877-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="df877-247">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-247">Int64</span></span>|  
|<span data-ttu-id="df877-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df877-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="df877-249">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-249">Int32</span></span>|  
|<span data-ttu-id="df877-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="df877-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="df877-251">Int16</span><span class="sxs-lookup"><span data-stu-id="df877-251">Int16</span></span>|  
|<span data-ttu-id="df877-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df877-252">DESCRIPTION</span></span>|<span data-ttu-id="df877-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-253">String</span></span>|  
|<span data-ttu-id="df877-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-254">TYPE_NAME</span></span>|<span data-ttu-id="df877-255">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-255">String</span></span>|  
|<span data-ttu-id="df877-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="df877-257">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="df877-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="df877-258">Catalog</span></span>  
  
|<span data-ttu-id="df877-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-259">ColumnName</span></span>|<span data-ttu-id="df877-260">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-261">CATALOG_NAME</span></span>|<span data-ttu-id="df877-262">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-262">String</span></span>|  
|<span data-ttu-id="df877-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df877-263">DESCRIPTION</span></span>|<span data-ttu-id="df877-264">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="df877-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="df877-265">Indexes</span></span>  
  
|<span data-ttu-id="df877-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-266">ColumnName</span></span>|<span data-ttu-id="df877-267">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-268">TABLE_CATALOG</span></span>|<span data-ttu-id="df877-269">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-269">String</span></span>|  
|<span data-ttu-id="df877-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="df877-271">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-271">String</span></span>|  
|<span data-ttu-id="df877-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-272">TABLE_NAME</span></span>|<span data-ttu-id="df877-273">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-273">String</span></span>|  
|<span data-ttu-id="df877-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-274">INDEX_CATALOG</span></span>|<span data-ttu-id="df877-275">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-275">String</span></span>|  
|<span data-ttu-id="df877-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="df877-277">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-277">String</span></span>|  
|<span data-ttu-id="df877-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-278">INDEX_NAME</span></span>|<span data-ttu-id="df877-279">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-279">String</span></span>|  
|<span data-ttu-id="df877-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="df877-280">PRIMARY_KEY</span></span>|<span data-ttu-id="df877-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-281">Boolean</span></span>|  
|<span data-ttu-id="df877-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="df877-282">UNIQUE</span></span>|<span data-ttu-id="df877-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-283">Boolean</span></span>|  
|<span data-ttu-id="df877-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="df877-284">CLUSTERED</span></span>|<span data-ttu-id="df877-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-285">Boolean</span></span>|  
|<span data-ttu-id="df877-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-286">TYPE</span></span>|<span data-ttu-id="df877-287">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-287">Int32</span></span>|  
|<span data-ttu-id="df877-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="df877-288">FILL_FACTOR</span></span>|<span data-ttu-id="df877-289">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-289">Int32</span></span>|  
|<span data-ttu-id="df877-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="df877-290">INITIAL_SIZE</span></span>|<span data-ttu-id="df877-291">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-291">Int32</span></span>|  
|<span data-ttu-id="df877-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="df877-292">NULLS</span></span>|<span data-ttu-id="df877-293">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-293">Int32</span></span>|  
|<span data-ttu-id="df877-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="df877-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="df877-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-295">Boolean</span></span>|  
|<span data-ttu-id="df877-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="df877-296">AUTO_UPDATE</span></span>|<span data-ttu-id="df877-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-297">Boolean</span></span>|  
|<span data-ttu-id="df877-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="df877-298">NULL_COLLATION</span></span>|<span data-ttu-id="df877-299">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-299">Int32</span></span>|  
|<span data-ttu-id="df877-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df877-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="df877-301">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-301">Int64</span></span>|  
|<span data-ttu-id="df877-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-302">COLUMN_NAME</span></span>|<span data-ttu-id="df877-303">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-303">String</span></span>|  
|<span data-ttu-id="df877-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="df877-304">COLUMN_GUID</span></span>|<span data-ttu-id="df877-305">Guid</span><span class="sxs-lookup"><span data-stu-id="df877-305">Guid</span></span>|  
|<span data-ttu-id="df877-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="df877-306">COLUMN_PROPID</span></span>|<span data-ttu-id="df877-307">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-307">Int64</span></span>|  
|<span data-ttu-id="df877-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="df877-308">COLLATION</span></span>|<span data-ttu-id="df877-309">Int16</span><span class="sxs-lookup"><span data-stu-id="df877-309">Int16</span></span>|  
|<span data-ttu-id="df877-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="df877-310">CARDINALITY</span></span>|<span data-ttu-id="df877-311">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="df877-311">Decimal</span></span>|  
|<span data-ttu-id="df877-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="df877-312">PAGES</span></span>|<span data-ttu-id="df877-313">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-313">Int32</span></span>|  
|<span data-ttu-id="df877-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="df877-314">FILTER_CONDITION</span></span>|<span data-ttu-id="df877-315">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-315">String</span></span>|  
|<span data-ttu-id="df877-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="df877-316">INTEGRATED</span></span>|<span data-ttu-id="df877-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="df877-318">Поставщик Microsoft OLE DB для Oracle</span><span class="sxs-lookup"><span data-stu-id="df877-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="df877-319">Драйвер OLE DB для Oracle (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="df877-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="df877-320">Таблицы</span><span class="sxs-lookup"><span data-stu-id="df877-320">Tables</span></span>  
  
-   <span data-ttu-id="df877-321">Столбцы</span><span class="sxs-lookup"><span data-stu-id="df877-321">Columns</span></span>  
  
-   <span data-ttu-id="df877-322">Процедуры</span><span class="sxs-lookup"><span data-stu-id="df877-322">Procedures</span></span>  
  
-   <span data-ttu-id="df877-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="df877-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="df877-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="df877-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="df877-325">Представления</span><span class="sxs-lookup"><span data-stu-id="df877-325">Views</span></span>  
  
-   <span data-ttu-id="df877-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="df877-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="df877-327">Таблицы</span><span class="sxs-lookup"><span data-stu-id="df877-327">Tables</span></span>  
  
|<span data-ttu-id="df877-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-328">ColumnName</span></span>|<span data-ttu-id="df877-329">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-330">TABLE_CATALOG</span></span>|<span data-ttu-id="df877-331">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-331">String</span></span>|  
|<span data-ttu-id="df877-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="df877-333">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-333">String</span></span>|  
|<span data-ttu-id="df877-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-334">TABLE_NAME</span></span>|<span data-ttu-id="df877-335">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-335">String</span></span>|  
|<span data-ttu-id="df877-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-336">TABLE_TYPE</span></span>|<span data-ttu-id="df877-337">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-337">String</span></span>|  
|<span data-ttu-id="df877-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="df877-338">TABLE_GUID</span></span>|<span data-ttu-id="df877-339">Guid</span><span class="sxs-lookup"><span data-stu-id="df877-339">Guid</span></span>|  
|<span data-ttu-id="df877-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df877-340">DESCRIPTION</span></span>|<span data-ttu-id="df877-341">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-341">String</span></span>|  
|<span data-ttu-id="df877-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="df877-342">TABLE_PROPID</span></span>|<span data-ttu-id="df877-343">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-343">Int64</span></span>|  
|<span data-ttu-id="df877-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df877-344">DATE_CREATED</span></span>|<span data-ttu-id="df877-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-345">DateTime</span></span>|  
|<span data-ttu-id="df877-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df877-346">DATE_MODIFIED</span></span>|<span data-ttu-id="df877-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="df877-348">Столбцы</span><span class="sxs-lookup"><span data-stu-id="df877-348">Columns</span></span>  
  
|<span data-ttu-id="df877-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-349">ColumnName</span></span>|<span data-ttu-id="df877-350">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-351">TABLE_CATALOG</span></span>|<span data-ttu-id="df877-352">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-352">String</span></span>|  
|<span data-ttu-id="df877-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="df877-354">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-354">String</span></span>|  
|<span data-ttu-id="df877-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-355">TABLE_NAME</span></span>|<span data-ttu-id="df877-356">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-356">String</span></span>|  
|<span data-ttu-id="df877-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-357">COLUMN_NAME</span></span>|<span data-ttu-id="df877-358">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-358">String</span></span>|  
|<span data-ttu-id="df877-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="df877-359">COLUMN_GUID</span></span>|<span data-ttu-id="df877-360">Guid</span><span class="sxs-lookup"><span data-stu-id="df877-360">Guid</span></span>|  
|<span data-ttu-id="df877-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="df877-361">COLUMN_PROPID</span></span>|<span data-ttu-id="df877-362">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-362">Int64</span></span>|  
|<span data-ttu-id="df877-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df877-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="df877-364">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-364">Int64</span></span>|  
|<span data-ttu-id="df877-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="df877-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="df877-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-366">Boolean</span></span>|  
|<span data-ttu-id="df877-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="df877-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="df877-368">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-368">String</span></span>|  
|<span data-ttu-id="df877-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="df877-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="df877-370">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-370">Int64</span></span>|  
|<span data-ttu-id="df877-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="df877-371">IS_NULLABLE</span></span>|<span data-ttu-id="df877-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-372">Boolean</span></span>|  
|<span data-ttu-id="df877-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-373">DATA_TYPE</span></span>|<span data-ttu-id="df877-374">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-374">Int32</span></span>|  
|<span data-ttu-id="df877-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="df877-375">TYPE_GUID</span></span>|<span data-ttu-id="df877-376">Guid</span><span class="sxs-lookup"><span data-stu-id="df877-376">Guid</span></span>|  
|<span data-ttu-id="df877-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df877-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="df877-378">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-378">Int64</span></span>|  
|<span data-ttu-id="df877-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df877-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="df877-380">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-380">Int64</span></span>|  
|<span data-ttu-id="df877-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df877-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="df877-382">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-382">Int32</span></span>|  
|<span data-ttu-id="df877-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="df877-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="df877-384">Int16</span><span class="sxs-lookup"><span data-stu-id="df877-384">Int16</span></span>|  
|<span data-ttu-id="df877-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df877-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="df877-386">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-386">Int64</span></span>|  
|<span data-ttu-id="df877-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="df877-388">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-388">String</span></span>|  
|<span data-ttu-id="df877-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="df877-390">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-390">String</span></span>|  
|<span data-ttu-id="df877-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="df877-392">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-392">String</span></span>|  
|<span data-ttu-id="df877-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="df877-394">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-394">String</span></span>|  
|<span data-ttu-id="df877-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="df877-396">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-396">String</span></span>|  
|<span data-ttu-id="df877-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-397">COLLATION_NAME</span></span>|<span data-ttu-id="df877-398">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-398">String</span></span>|  
|<span data-ttu-id="df877-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="df877-400">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-400">String</span></span>|  
|<span data-ttu-id="df877-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="df877-402">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-402">String</span></span>|  
|<span data-ttu-id="df877-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-403">DOMAIN_NAME</span></span>|<span data-ttu-id="df877-404">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-404">String</span></span>|  
|<span data-ttu-id="df877-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df877-405">DESCRIPTION</span></span>|<span data-ttu-id="df877-406">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="df877-407">Процедуры</span><span class="sxs-lookup"><span data-stu-id="df877-407">Procedures</span></span>  
  
|<span data-ttu-id="df877-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-408">ColumnName</span></span>|<span data-ttu-id="df877-409">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="df877-411">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-411">String</span></span>|  
|<span data-ttu-id="df877-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="df877-413">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-413">String</span></span>|  
|<span data-ttu-id="df877-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="df877-415">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-415">String</span></span>|  
|<span data-ttu-id="df877-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="df877-417">Int16</span><span class="sxs-lookup"><span data-stu-id="df877-417">Int16</span></span>|  
|<span data-ttu-id="df877-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="df877-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="df877-419">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-419">String</span></span>|  
|<span data-ttu-id="df877-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df877-420">DESCRIPTION</span></span>|<span data-ttu-id="df877-421">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-421">String</span></span>|  
|<span data-ttu-id="df877-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df877-422">DATE_CREATED</span></span>|<span data-ttu-id="df877-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-423">DateTime</span></span>|  
|<span data-ttu-id="df877-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df877-424">DATE_MODIFIED</span></span>|<span data-ttu-id="df877-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="df877-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="df877-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="df877-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-427">ColumnName</span></span>|<span data-ttu-id="df877-428">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="df877-430">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-430">String</span></span>|  
|<span data-ttu-id="df877-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="df877-432">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-432">String</span></span>|  
|<span data-ttu-id="df877-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="df877-434">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-434">String</span></span>|  
|<span data-ttu-id="df877-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-435">COLUMN_NAME</span></span>|<span data-ttu-id="df877-436">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-436">String</span></span>|  
|<span data-ttu-id="df877-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="df877-437">COLUMN_GUID</span></span>|<span data-ttu-id="df877-438">Guid</span><span class="sxs-lookup"><span data-stu-id="df877-438">Guid</span></span>|  
|<span data-ttu-id="df877-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="df877-439">COLUMN_PROPID</span></span>|<span data-ttu-id="df877-440">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-440">Int64</span></span>|  
|<span data-ttu-id="df877-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="df877-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="df877-442">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-442">Int64</span></span>|  
|<span data-ttu-id="df877-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df877-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="df877-444">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-444">Int64</span></span>|  
|<span data-ttu-id="df877-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="df877-445">IS_NULLABLE</span></span>|<span data-ttu-id="df877-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-446">Boolean</span></span>|  
|<span data-ttu-id="df877-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-447">DATA_TYPE</span></span>|<span data-ttu-id="df877-448">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-448">Int32</span></span>|  
|<span data-ttu-id="df877-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="df877-449">TYPE_GUID</span></span>|<span data-ttu-id="df877-450">Guid</span><span class="sxs-lookup"><span data-stu-id="df877-450">Guid</span></span>|  
|<span data-ttu-id="df877-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df877-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="df877-452">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-452">Int64</span></span>|  
|<span data-ttu-id="df877-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df877-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="df877-454">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-454">Int64</span></span>|  
|<span data-ttu-id="df877-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df877-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="df877-456">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-456">Int32</span></span>|  
|<span data-ttu-id="df877-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="df877-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="df877-458">Int16</span><span class="sxs-lookup"><span data-stu-id="df877-458">Int16</span></span>|  
|<span data-ttu-id="df877-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df877-459">DESCRIPTION</span></span>|<span data-ttu-id="df877-460">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-460">String</span></span>|  
|<span data-ttu-id="df877-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="df877-461">OVERLOAD</span></span>|<span data-ttu-id="df877-462">Int16</span><span class="sxs-lookup"><span data-stu-id="df877-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="df877-463">Представления</span><span class="sxs-lookup"><span data-stu-id="df877-463">Views</span></span>  
  
|<span data-ttu-id="df877-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-464">ColumnName</span></span>|<span data-ttu-id="df877-465">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-466">TABLE_CATALOG</span></span>|<span data-ttu-id="df877-467">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-467">String</span></span>|  
|<span data-ttu-id="df877-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="df877-469">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-469">String</span></span>|  
|<span data-ttu-id="df877-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-470">TABLE_NAME</span></span>|<span data-ttu-id="df877-471">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-471">String</span></span>|  
|<span data-ttu-id="df877-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="df877-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="df877-473">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-473">String</span></span>|  
|<span data-ttu-id="df877-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="df877-474">CHECK_OPTION</span></span>|<span data-ttu-id="df877-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-475">Boolean</span></span>|  
|<span data-ttu-id="df877-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="df877-476">IS_UPDATABLE</span></span>|<span data-ttu-id="df877-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-477">Boolean</span></span>|  
|<span data-ttu-id="df877-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df877-478">DESCRIPTION</span></span>|<span data-ttu-id="df877-479">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-479">String</span></span>|  
|<span data-ttu-id="df877-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df877-480">DATE_CREATED</span></span>|<span data-ttu-id="df877-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-481">DateTime</span></span>|  
|<span data-ttu-id="df877-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df877-482">DATE_MODIFIED</span></span>|<span data-ttu-id="df877-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="df877-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="df877-484">Indexes</span></span>  
  
|<span data-ttu-id="df877-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-485">ColumnName</span></span>|<span data-ttu-id="df877-486">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-487">TABLE_CATALOG</span></span>|<span data-ttu-id="df877-488">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-488">String</span></span>|  
|<span data-ttu-id="df877-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="df877-490">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-490">String</span></span>|  
|<span data-ttu-id="df877-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-491">TABLE_NAME</span></span>|<span data-ttu-id="df877-492">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-492">String</span></span>|  
|<span data-ttu-id="df877-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-493">INDEX_CATALOG</span></span>|<span data-ttu-id="df877-494">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-494">String</span></span>|  
|<span data-ttu-id="df877-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="df877-496">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-496">String</span></span>|  
|<span data-ttu-id="df877-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-497">INDEX_NAME</span></span>|<span data-ttu-id="df877-498">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-498">String</span></span>|  
|<span data-ttu-id="df877-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="df877-499">PRIMARY_KEY</span></span>|<span data-ttu-id="df877-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-500">Boolean</span></span>|  
|<span data-ttu-id="df877-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="df877-501">UNIQUE</span></span>|<span data-ttu-id="df877-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-502">Boolean</span></span>|  
|<span data-ttu-id="df877-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="df877-503">CLUSTERED</span></span>|<span data-ttu-id="df877-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-504">Boolean</span></span>|  
|<span data-ttu-id="df877-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-505">TYPE</span></span>|<span data-ttu-id="df877-506">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-506">Int32</span></span>|  
|<span data-ttu-id="df877-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="df877-507">FILL_FACTOR</span></span>|<span data-ttu-id="df877-508">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-508">Int32</span></span>|  
|<span data-ttu-id="df877-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="df877-509">INITIAL_SIZE</span></span>|<span data-ttu-id="df877-510">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-510">Int32</span></span>|  
|<span data-ttu-id="df877-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="df877-511">NULLS</span></span>|<span data-ttu-id="df877-512">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-512">Int32</span></span>|  
|<span data-ttu-id="df877-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="df877-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="df877-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-514">Boolean</span></span>|  
|<span data-ttu-id="df877-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="df877-515">AUTO_UPDATE</span></span>|<span data-ttu-id="df877-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-516">Boolean</span></span>|  
|<span data-ttu-id="df877-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="df877-517">NULL_COLLATION</span></span>|<span data-ttu-id="df877-518">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-518">Int32</span></span>|  
|<span data-ttu-id="df877-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df877-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="df877-520">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-520">Int64</span></span>|  
|<span data-ttu-id="df877-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-521">COLUMN_NAME</span></span>|<span data-ttu-id="df877-522">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-522">String</span></span>|  
|<span data-ttu-id="df877-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="df877-523">COLUMN_GUID</span></span>|<span data-ttu-id="df877-524">Guid</span><span class="sxs-lookup"><span data-stu-id="df877-524">Guid</span></span>|  
|<span data-ttu-id="df877-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="df877-525">COLUMN_PROPID</span></span>|<span data-ttu-id="df877-526">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-526">Int64</span></span>|  
|<span data-ttu-id="df877-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="df877-527">COLLATION</span></span>|<span data-ttu-id="df877-528">Int16</span><span class="sxs-lookup"><span data-stu-id="df877-528">Int16</span></span>|  
|<span data-ttu-id="df877-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="df877-529">CARDINALITY</span></span>|<span data-ttu-id="df877-530">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="df877-530">Decimal</span></span>|  
|<span data-ttu-id="df877-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="df877-531">PAGES</span></span>|<span data-ttu-id="df877-532">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-532">Int32</span></span>|  
|<span data-ttu-id="df877-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="df877-533">FILTER_CONDITION</span></span>|<span data-ttu-id="df877-534">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-534">String</span></span>|  
|<span data-ttu-id="df877-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="df877-535">INTEGRATED</span></span>|<span data-ttu-id="df877-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="df877-537">Поставщик OLE DB для Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="df877-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="df877-538">Драйвер OLE DB для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="df877-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="df877-539">Таблицы</span><span class="sxs-lookup"><span data-stu-id="df877-539">Tables</span></span>  
  
-   <span data-ttu-id="df877-540">Столбцы</span><span class="sxs-lookup"><span data-stu-id="df877-540">Columns</span></span>  
  
-   <span data-ttu-id="df877-541">Процедуры</span><span class="sxs-lookup"><span data-stu-id="df877-541">Procedures</span></span>  
  
-   <span data-ttu-id="df877-542">Представления</span><span class="sxs-lookup"><span data-stu-id="df877-542">Views</span></span>  
  
-   <span data-ttu-id="df877-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="df877-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="df877-544">Таблицы</span><span class="sxs-lookup"><span data-stu-id="df877-544">Tables</span></span>  
  
|<span data-ttu-id="df877-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-545">ColumnName</span></span>|<span data-ttu-id="df877-546">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-547">TABLE_CATALOG</span></span>|<span data-ttu-id="df877-548">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-548">String</span></span>|  
|<span data-ttu-id="df877-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="df877-550">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-550">String</span></span>|  
|<span data-ttu-id="df877-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-551">TABLE_NAME</span></span>|<span data-ttu-id="df877-552">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-552">String</span></span>|  
|<span data-ttu-id="df877-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-553">TABLE_TYPE</span></span>|<span data-ttu-id="df877-554">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-554">String</span></span>|  
|<span data-ttu-id="df877-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="df877-555">TABLE_GUID</span></span>|<span data-ttu-id="df877-556">Guid</span><span class="sxs-lookup"><span data-stu-id="df877-556">Guid</span></span>|  
|<span data-ttu-id="df877-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df877-557">DESCRIPTION</span></span>|<span data-ttu-id="df877-558">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-558">String</span></span>|  
|<span data-ttu-id="df877-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="df877-559">TABLE_PROPID</span></span>|<span data-ttu-id="df877-560">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-560">Int64</span></span>|  
|<span data-ttu-id="df877-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df877-561">DATE_CREATED</span></span>|<span data-ttu-id="df877-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-562">DateTime</span></span>|  
|<span data-ttu-id="df877-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df877-563">DATE_MODIFIED</span></span>|<span data-ttu-id="df877-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="df877-565">Столбцы</span><span class="sxs-lookup"><span data-stu-id="df877-565">Columns</span></span>  
  
|<span data-ttu-id="df877-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-566">ColumnName</span></span>|<span data-ttu-id="df877-567">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-568">TABLE_CATALOG</span></span>|<span data-ttu-id="df877-569">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-569">String</span></span>|  
|<span data-ttu-id="df877-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="df877-571">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-571">String</span></span>|  
|<span data-ttu-id="df877-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-572">TABLE_NAME</span></span>|<span data-ttu-id="df877-573">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-573">String</span></span>|  
|<span data-ttu-id="df877-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-574">COLUMN_NAME</span></span>|<span data-ttu-id="df877-575">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-575">String</span></span>|  
|<span data-ttu-id="df877-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="df877-576">COLUMN_GUID</span></span>|<span data-ttu-id="df877-577">Guid</span><span class="sxs-lookup"><span data-stu-id="df877-577">Guid</span></span>|  
|<span data-ttu-id="df877-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="df877-578">COLUMN_PROPID</span></span>|<span data-ttu-id="df877-579">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-579">Int64</span></span>|  
|<span data-ttu-id="df877-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df877-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="df877-581">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-581">Int64</span></span>|  
|<span data-ttu-id="df877-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="df877-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="df877-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-583">Boolean</span></span>|  
|<span data-ttu-id="df877-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="df877-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="df877-585">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-585">String</span></span>|  
|<span data-ttu-id="df877-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="df877-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="df877-587">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-587">Int64</span></span>|  
|<span data-ttu-id="df877-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="df877-588">IS_NULLABLE</span></span>|<span data-ttu-id="df877-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-589">Boolean</span></span>|  
|<span data-ttu-id="df877-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-590">DATA_TYPE</span></span>|<span data-ttu-id="df877-591">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-591">Int32</span></span>|  
|<span data-ttu-id="df877-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="df877-592">TYPE_GUID</span></span>|<span data-ttu-id="df877-593">Guid</span><span class="sxs-lookup"><span data-stu-id="df877-593">Guid</span></span>|  
|<span data-ttu-id="df877-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df877-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="df877-595">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-595">Int64</span></span>|  
|<span data-ttu-id="df877-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df877-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="df877-597">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-597">Int64</span></span>|  
|<span data-ttu-id="df877-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df877-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="df877-599">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-599">Int32</span></span>|  
|<span data-ttu-id="df877-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="df877-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="df877-601">Int16</span><span class="sxs-lookup"><span data-stu-id="df877-601">Int16</span></span>|  
|<span data-ttu-id="df877-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df877-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="df877-603">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-603">Int64</span></span>|  
|<span data-ttu-id="df877-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="df877-605">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-605">String</span></span>|  
|<span data-ttu-id="df877-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="df877-607">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-607">String</span></span>|  
|<span data-ttu-id="df877-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="df877-609">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-609">String</span></span>|  
|<span data-ttu-id="df877-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="df877-611">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-611">String</span></span>|  
|<span data-ttu-id="df877-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="df877-613">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-613">String</span></span>|  
|<span data-ttu-id="df877-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-614">COLLATION_NAME</span></span>|<span data-ttu-id="df877-615">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-615">String</span></span>|  
|<span data-ttu-id="df877-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="df877-617">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-617">String</span></span>|  
|<span data-ttu-id="df877-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="df877-619">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-619">String</span></span>|  
|<span data-ttu-id="df877-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-620">DOMAIN_NAME</span></span>|<span data-ttu-id="df877-621">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-621">String</span></span>|  
|<span data-ttu-id="df877-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df877-622">DESCRIPTION</span></span>|<span data-ttu-id="df877-623">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="df877-624">Процедуры</span><span class="sxs-lookup"><span data-stu-id="df877-624">Procedures</span></span>  
  
|<span data-ttu-id="df877-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-625">ColumnName</span></span>|<span data-ttu-id="df877-626">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="df877-628">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-628">String</span></span>|  
|<span data-ttu-id="df877-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="df877-630">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-630">String</span></span>|  
|<span data-ttu-id="df877-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="df877-632">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-632">String</span></span>|  
|<span data-ttu-id="df877-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="df877-634">Int16</span><span class="sxs-lookup"><span data-stu-id="df877-634">Int16</span></span>|  
|<span data-ttu-id="df877-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="df877-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="df877-636">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-636">String</span></span>|  
|<span data-ttu-id="df877-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df877-637">DESCRIPTION</span></span>|<span data-ttu-id="df877-638">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-638">String</span></span>|  
|<span data-ttu-id="df877-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df877-639">DATE_CREATED</span></span>|<span data-ttu-id="df877-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-640">DateTime</span></span>|  
|<span data-ttu-id="df877-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df877-641">DATE_MODIFIED</span></span>|<span data-ttu-id="df877-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="df877-643">Представления</span><span class="sxs-lookup"><span data-stu-id="df877-643">Views</span></span>  
  
|<span data-ttu-id="df877-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-644">ColumnName</span></span>|<span data-ttu-id="df877-645">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-646">TABLE_CATALOG</span></span>|<span data-ttu-id="df877-647">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-647">String</span></span>|  
|<span data-ttu-id="df877-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="df877-649">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-649">String</span></span>|  
|<span data-ttu-id="df877-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-650">TABLE_NAME</span></span>|<span data-ttu-id="df877-651">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-651">String</span></span>|  
|<span data-ttu-id="df877-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="df877-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="df877-653">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-653">String</span></span>|  
|<span data-ttu-id="df877-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="df877-654">CHECK_OPTION</span></span>|<span data-ttu-id="df877-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-655">Boolean</span></span>|  
|<span data-ttu-id="df877-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="df877-656">IS_UPDATABLE</span></span>|<span data-ttu-id="df877-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-657">Boolean</span></span>|  
|<span data-ttu-id="df877-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df877-658">DESCRIPTION</span></span>|<span data-ttu-id="df877-659">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-659">String</span></span>|  
|<span data-ttu-id="df877-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df877-660">DATE_CREATED</span></span>|<span data-ttu-id="df877-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-661">DateTime</span></span>|  
|<span data-ttu-id="df877-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df877-662">DATE_MODIFIED</span></span>|<span data-ttu-id="df877-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="df877-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="df877-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="df877-664">Indexes</span></span>  
  
|<span data-ttu-id="df877-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="df877-665">ColumnName</span></span>|<span data-ttu-id="df877-666">DataType</span><span class="sxs-lookup"><span data-stu-id="df877-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df877-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-667">TABLE_CATALOG</span></span>|<span data-ttu-id="df877-668">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-668">String</span></span>|  
|<span data-ttu-id="df877-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="df877-670">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-670">String</span></span>|  
|<span data-ttu-id="df877-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-671">TABLE_NAME</span></span>|<span data-ttu-id="df877-672">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-672">String</span></span>|  
|<span data-ttu-id="df877-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df877-673">INDEX_CATALOG</span></span>|<span data-ttu-id="df877-674">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-674">String</span></span>|  
|<span data-ttu-id="df877-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df877-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="df877-676">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-676">String</span></span>|  
|<span data-ttu-id="df877-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-677">INDEX_NAME</span></span>|<span data-ttu-id="df877-678">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-678">String</span></span>|  
|<span data-ttu-id="df877-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="df877-679">PRIMARY_KEY</span></span>|<span data-ttu-id="df877-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-680">Boolean</span></span>|  
|<span data-ttu-id="df877-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="df877-681">UNIQUE</span></span>|<span data-ttu-id="df877-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-682">Boolean</span></span>|  
|<span data-ttu-id="df877-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="df877-683">CLUSTERED</span></span>|<span data-ttu-id="df877-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-684">Boolean</span></span>|  
|<span data-ttu-id="df877-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="df877-685">TYPE</span></span>|<span data-ttu-id="df877-686">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-686">Int32</span></span>|  
|<span data-ttu-id="df877-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="df877-687">FILL_FACTOR</span></span>|<span data-ttu-id="df877-688">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-688">Int32</span></span>|  
|<span data-ttu-id="df877-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="df877-689">INITIAL_SIZE</span></span>|<span data-ttu-id="df877-690">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-690">Int32</span></span>|  
|<span data-ttu-id="df877-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="df877-691">NULLS</span></span>|<span data-ttu-id="df877-692">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-692">Int32</span></span>|  
|<span data-ttu-id="df877-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="df877-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="df877-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-694">Boolean</span></span>|  
|<span data-ttu-id="df877-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="df877-695">AUTO_UPDATE</span></span>|<span data-ttu-id="df877-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-696">Boolean</span></span>|  
|<span data-ttu-id="df877-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="df877-697">NULL_COLLATION</span></span>|<span data-ttu-id="df877-698">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-698">Int32</span></span>|  
|<span data-ttu-id="df877-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df877-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="df877-700">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-700">Int64</span></span>|  
|<span data-ttu-id="df877-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df877-701">COLUMN_NAME</span></span>|<span data-ttu-id="df877-702">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-702">String</span></span>|  
|<span data-ttu-id="df877-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="df877-703">COLUMN_GUID</span></span>|<span data-ttu-id="df877-704">Guid</span><span class="sxs-lookup"><span data-stu-id="df877-704">Guid</span></span>|  
|<span data-ttu-id="df877-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="df877-705">COLUMN_PROPID</span></span>|<span data-ttu-id="df877-706">Int64</span><span class="sxs-lookup"><span data-stu-id="df877-706">Int64</span></span>|  
|<span data-ttu-id="df877-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="df877-707">COLLATION</span></span>|<span data-ttu-id="df877-708">Int16</span><span class="sxs-lookup"><span data-stu-id="df877-708">Int16</span></span>|  
|<span data-ttu-id="df877-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="df877-709">CARDINALITY</span></span>|<span data-ttu-id="df877-710">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="df877-710">Decimal</span></span>|  
|<span data-ttu-id="df877-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="df877-711">PAGES</span></span>|<span data-ttu-id="df877-712">Int32</span><span class="sxs-lookup"><span data-stu-id="df877-712">Int32</span></span>|  
|<span data-ttu-id="df877-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="df877-713">FILTER_CONDITION</span></span>|<span data-ttu-id="df877-714">Строковое</span><span class="sxs-lookup"><span data-stu-id="df877-714">String</span></span>|  
|<span data-ttu-id="df877-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="df877-715">INTEGRATED</span></span>|<span data-ttu-id="df877-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="df877-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df877-717">См. также</span><span class="sxs-lookup"><span data-stu-id="df877-717">See Also</span></span>  
 [<span data-ttu-id="df877-718">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="df877-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
