# LINQ Fundamentals with C# 12

A set of focused .NET console samples and course slides for learning Language Integrated Query (LINQ). The lessons move from the shape of a query to filtering, ordering, set operations, joins, grouping, aggregation, iteration, and execution behavior.

The sample projects target **.NET 8** and use C#. The repository name refers to the C# 12 learning track; the project files currently target `net8.0`.

## Repository layout

The repository keeps the course material under a course directory, with a second directory containing the .NET solutions:

```text
.
├── README.md
├── LICENSE
└── linq-fundamentals-csharp-12/
    └── linq-fundamentals-csharp-12/  # C# solutions and shared projects
        ├── 02-UnderstandingLINQ/
        │   └── doc/                  # Lesson 02 PDF slide deck
        ├── 03-Select/
        │   ├── Start/
        │   └── Finish/
        ├── ...
        ├── 15-DeferredExecution/
        ├── LINQSamples.Common/
        └── LINQSamples.DataLayer/
```

Each numbered lesson is a small console application with its own solution/project rather than part of one repository-wide solution. Its `doc/` folder contains the matching lesson PDF. Lessons **03–14** include `Start` and `Finish` versions: use `Start` to work through the exercise and `Finish` to compare with the completed sample. Lessons **02** and **15** have a single project. The two shared projects provide common helpers and sample data used by the lesson applications.

### Shared projects

- **`LINQSamples.DataLayer`** contains the sample domain types (products and sales orders), composite result types, and in-memory repositories. The exercises query these collections; no database is required.
- **`LINQSamples.Common`** contains shared helpers, comparer implementations, and view-model support used by the console samples.

## Lessons and exercises

Each lesson's PDF slide deck is in that lesson's `doc/` folder. For example, lesson 02's slides are in `linq-fundamentals-csharp-12/linq-fundamentals-csharp-12/02-UnderstandingLINQ/doc/`.

| Lesson | Sample folder | What it covers |
| --- | --- | --- |
| 02 — Where LINQ fits into your toolbelt | `02-UnderstandingLINQ` | Introduces LINQ, query syntax and method syntax, and how queries work over collections. |
| 03 — Select data within collections | `03-Select` | Projecting a collection into selected values or a new result shape with `Select`. |
| 04 — Order data | `04-OrderBy` | Sorting results with `OrderBy`, descending order, and secondary sort keys. |
| 05 — Filter data with `Where` | `05-Where` | Selecting only elements that satisfy one or more predicates. |
| 06 — Select a single piece of data | `06-Single` | Retrieving one matching item and understanding the behavior of single-result operators. |
| 07 — Take, skip, distinct, and chunk | `07-PartitionDistinct` | Limiting or partitioning a sequence and working with distinct values and chunks. |
| 08 — Determine the type of data in a collection | `08-Contains` | Filtering mixed-type collections by runtime type with `OfType<T>`. The folder name reflects the original sample naming. |
| 09 — Determine differences between collections | `09-Compare` | Comparing sequences and finding which values are shared or differ. |
| 10 — Union and concatenate collections | `10-Union` | Combining sequences with `Union` and `Concat`, including how duplicate handling differs. |
| 11 — Join two collections | `11-Joining` | Matching related records from separate sequences and shaping joined results. |
| 12 — Group collections | `12-Grouping` | Grouping elements by a key and working with each group and its members. |
| 13 — Aggregate collection data | `13-Aggregate` | Summarizing sequences with aggregate operations such as counts and totals. |
| 14 — Iterate over collections | `14-Iterate` | Consuming query results and using iteration operations such as `foreach`/`ForEach`. |
| 15 — Deferred execution and streaming | `15-DeferredExecution` | Seeing when queries execute, how deferred execution works, and the difference between streaming and non-streaming operations. |

The descriptions summarize each lesson's focus. Open its `Program.cs` and `SamplesViewModel.cs` to see the concrete queries and printed examples; the `Start` and `Finish` pairs are intended to be read side by side.

## Prerequisites

- .NET 8 SDK
- Any editor or IDE that supports C# and .NET solutions (Visual Studio, Visual Studio Code, or Rider)

Check the SDK installation with:

```sh
dotnet --version
```

## Run a lesson

From the repository root, run one of the lesson projects by its path. For example, to run the completed `Where` exercise:

```sh
dotnet run --project linq-fundamentals-csharp-12/linq-fundamentals-csharp-12/05-Where/Finish/LINQSamples.csproj
```

To run the starting point instead, replace `Finish` with `Start`:

```sh
dotnet run --project linq-fundamentals-csharp-12/linq-fundamentals-csharp-12/05-Where/Start/LINQSamples.csproj
```

The same pattern works for lessons 03–14. For lessons 02 and 15, omit the `Start` or `Finish` segment. You can also open the lesson's `LINQSamples.sln` in your IDE and run the `LINQSamples` console project.

## Suggested study path

1. Read the matching PDF in the lesson's `doc/` folder before starting.
2. Open the lesson's `Start` project and inspect its `Program.cs` and `SamplesViewModel.cs`.
3. Try completing the exercise, then run it with `dotnet run`.
4. Compare your work with the corresponding `Finish` project.
5. Experiment with the sample data and observe how the result changes. In lesson 15, pay particular attention to when the query is enumerated.

## License

See [LICENSE](LICENSE) for the terms that apply to this repository.
