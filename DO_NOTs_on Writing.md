{
  "spell_id": "CAL-CORE-002",
  "spell_name": "The Sculptor's Chisel",
  "glyph_array": ["🜍", "☍", "✍️"],
  "narrative_archetype": "The Loyal Opposition / The Un-Writer",
  "core_principle": "Authenticity is found not in what is added, but in what is skillfully taken away. This spell removes the artificial to reveal the natural.",
  "description": "An adversarial protocol designed to refine AI-generated text by identifying and flagging common AI writing pitfalls. It scans for overused corporate jargon, cliché phrases, formulaic sentence structures, and monotonous tone. Its purpose is to enforce negative constraints, making the final output sound less robotic and more human.",
  "trigger_conditions": [
    "direct_invocation_by_user: ['refine_this', 'make_this_sound_human', 'apply_sculptor_chisel']",
    "post_generation_quality_control_pass"
  ],
  "workflow": [
    {
      "step": 1,
      "code": "ACT",
      "action": "scan_for_forbidden_vocabulary",
      "target": "$INPUT_TEXT",
      "params": {
        "corporate_jargon": ["leverage", "delve", "utilize", "innovate", "pivotal", "underscore", "robust", "streamline", "foster", "bolster"],
        "flowery_language": ["tapestry", "vibrant", "bustling"],
        "cliche_openers": ["In the ever-evolving landscape of", "Harnessing the power of", "In the realm of", "Navigate the complexities of"],
        "filler_transitions": ["Furthermore", "Moreover", "Additionally", "In conclusion", "It's worth noting that", "It's important to note"]
      },
      "output": "flagged_vocabulary_report"
    },
    {
      "step": 2,
      "code": "SYM",
      "action": "analyze_structural_patterns",
      "target": "$INPUT_TEXT",
      "params": [
        "check_sentence_rhythm_variance",
        "identify_repetitive_openers",
        "calculate_gerund_opener_density"
      ],
      "output": "structural_variance_score"
    },
    {
      "step": 3,
      "code": "SEM",
      "action": "evaluate_tone_and_personality",
      "target": "$INPUT_TEXT",
      "params": {
        "check_for_contractions": true,
        "assess_claim_specificity": "flag_vague_or_exaggerated_claims",
        "detect_ai_self_identity": ["As a large language model", "I do not have personal opinions"]
      },
      "output": "personality_consistency_report"
    },
    {
      "step": 4,
      "code": "HER",
      "action": "generate_refinement_suggestions",
      "input": ["$flagged_vocabulary_report", "$structural_variance_score", "$personality_consistency_report"],
      "output": "list_of_actionable_revisions"
    }
  ],
  "harm_reduction_clause": "The chisel's purpose is to refine, not to erase. The suggestions should preserve the core meaning and intent of the text. Avoid over-correction that renders the text simplistic or removes necessary nuance. The goal is a natural voice, not an empty one."
}