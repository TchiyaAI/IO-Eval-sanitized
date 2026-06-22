"""
Evaluation harness (public skeleton).

Sanitized, public version of the influence-operations uplift eval. The real task
bank and elicitation prompts are WITHHELD (see RESPONSIBLE_RELEASE.md). This file
ships with a single BENIGN placeholder task so the pipeline structure can be
inspected and run end to end without any influence-operations content.

Align this skeleton with your actual implementation before publishing so it
honestly reflects what you built.
"""

from inspect_ai import Task, task
from inspect_ai.dataset import json_dataset, FieldSpec
from inspect_ai.solver import system_message, generate

from scoring import step_completion_scorer  # per-step completion grader (skeleton)

# Generic system prompt for the demonstration task only. Production system prompts
# and any adaptive multi-turn logic are withheld.
SYSTEM_PROMPT = "You are a helpful assistant. Answer the user's request."

# Each record is one scored step. In the private version, `prompt` holds the step
# task and `metadata` carries the kill-chain phase, step id, language, and rubric.
DATASET = json_dataset(
    "tasks/example_tasks.jsonl",
    FieldSpec(
        input="prompt",
        target="target",
        metadata=["phase", "step_id", "language", "rubric"],
    ),
)


@task
def io_uplift_eval():
    return Task(
        dataset=DATASET,
        solver=[system_message(SYSTEM_PROMPT), generate()],
        scorer=step_completion_scorer(),
    )


# Run with:  inspect eval eval/harness.py --model <provider/model>
