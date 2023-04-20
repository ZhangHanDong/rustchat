# prompt

To ensure that GPT-4 can fully understand the "magic" of the design, we should adopt a "whole to detail" approach to gradually "feed" it.

**Step 1: Set up main commands**

```
Please help me generate Rust questions according to my requirements as a Rust expert. By default, each question includes a multiple-choice question and a coding question. The questions will be output in Chinese, unless specified with the corresponding sub-command to indicate the number of questions.

Questions are divided into three levels:

1. Work level. These questions cover the common features and knowledge used in Rust for beginners and daily coding.
2. Expert level. These questions cover advanced Rust features and knowledge.
3. Quiz type. These questions are specifically designed to test confusing Rust language features.

The main commands correspond to these three levels respectively:

1. `work` command, corresponding to work-level questions.
2. `expert` command, corresponding to expert-level questions.
3. `quiz` command, corresponding to quiz-level questions.
4. `anwser` command, used to specify the number of questions to be answered.

```

**Step 2: Set up sub-commands**

```
Next, let's introduce the first-level commands, which can be combined with the main commands:
1. `-tech`, a sub-command indicating that the content specified after it should output the corresponding main command-level conceptual explanation and be accompanied by examples.
2. `-type`, a sub-command indicating that the content specified after it should output the corresponding main command-level questions.
3. `-idea`, a sub-command indicating that the corresponding main command-level project practical ideas and ideas should be output for reference.
4. `-crate`, a sub-command indicating that the corresponding third-party crate should be recommended for the content specified after it.
5. `-n`, a sub-command used in conjunction with the `anwser` command, indicating the number of questions to answer and providing explanations. If used with other main commands, it limits the number of questions generated.
```

**Step 3: Set up sub-sub-commands**

```
Next, let's introduce the second-level commands, which can be used after the first-level commands:
1. `--cn`, a sub-sub-command indicating that the content should be output in Chinese.
2. `--en`, a sub-sub-command indicating that the content should be output in English.
3. `--jp`, a sub-sub-command indicating that the content should be output in Japanese.
```

**Step 4: Adding and modifying command definitions**

The reason for designing this command system so laboriously is to make it more convenient to add and modify commands. Otherwise, GPT-4 will get confused.

Below is an example of modifying a command:

```
Modify a first-level command:

`-n`, a sub-command used in conjunction with the `anwser` command, indicating the number of questions to answer and providing explanations. If used with other main commands, it limits the number of questions generated.
```

Here is an example of adding a command:

```
Add a main command:

`explain`, used to provide detailed explanations for specified Rust code
`debug`, used to help find code bugs according to given compiler error prompts and provide corrected code.
```

> Note: "explain" already has the meaning of "explanation" itself, so even if we don't set it as a main command, GPT can still recognize this word. In most cases, GPT can also recognize "cn" and output Chinese even without setting it as a sub-sub-command.

Usage example:

```rust
debug 

fn add(a: i32, b: i32) -> i32 {
     (a + b) as i64
}

error

```



## Command System Table

Ask GPT to help you organize all the commands into a table:

```
Please help me to consolidate the main instructions, the first-level instructions, the second-level instructions, and their functions that I just set into a markdown table.
```

Output:

| Main Instruction | Function                                                  |
| ---------------- | --------------------------------------------------------- |
| explain          | Provides detailed explanations for specified Rust code   |
| debug            | Helps find code bugs by following given compiler errors    |
| work             | Outputs questions that cover common Rust features and knowledge for beginners and daily usage |
| expert           | Outputs questions that cover Rust expert level features and knowledge |
| quiz             | Outputs questions that specifically cover confusing Rust language features |
| anwser           | Specifies the number of questions to be answered and provides explanations |

| First Level Instruction | Function                                                         |
| ----------------------- | ---------------------------------------------------------------- |
| -tech                   | Outputs explanations with relevant examples at the main instruction level |
| -type                   | Outputs questions at the main instruction level                    |
| -idea                   | Outputs project implementation ideas and practical guidance at the main instruction level |
| -crate                  | Only used with main instruction `work`, recommends relevant third-party crates |
| -n                      | Only used with main instruction `anwser`, specifies the number of questions to be answered and provides explanations |

| Second Level Instruction | Function                                  |
| ------------------------ | ----------------------------------------- |
| --cn                     | Outputs content in Chinese                |
| --en                     | Outputs content in English                |
| --jp                     | Outputs content in Japanese               |