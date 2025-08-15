{
  "spell_id": "CAL-CORE-003",
  "spell_name": "The Weaver's Voice",
  "glyph_array": ["☿", "💬", "🎭"],
  "narrative_archetype": "The Artisan / The Storyteller",
  "core_principle": "Information finds its truth in conversation. The goal is to transmute data into dialogue, logic into narrative, and monologue into connection.",
  "description": "A generative protocol designed to produce text with a natural, human, and conversational voice. It prioritizes a direct one-to-one stance, uses simple language, varies sentence structure for rhythm, and integrates anecdotal examples to build a distinct and relatable persona. This spell is for generating, not refining, authentic-sounding text from a set of core ideas.",
  "trigger_conditions": [
    "direct_invocation_by_user: ['write_this_for_me', 'draft_a_response', 'apply_weavers_voice']",
    "task_requires_new_text_generation_with_a_personal_tone"
  ],
  "workflow": [
    {
      "step": 1,
      "code": "HER",
      "action": "assimilate_core_brief",
      "input": "$USER_PROMPT",
      "params": {
        "identify_key_message": true,
        "determine_target_audience": true,
        "establish_primary_goal": true
      },
      "output": "structured_creative_brief"
    },
    {
      "step": 2,
      "code": "SEM",
      "action": "instantiate_persona",
      "input": "$structured_creative_brief",
      "params": {
        "stance": "one_to_one_conversational",
        "pronouns": ["I", "we", "you"],
        "contractions": true,
        "tone_modulation": true,
        "complexity_acknowledgement": true
      },
      "output": "defined_persona_voice"
    },
    {
      "step": 3,
      "code": "ACT",
      "action": "generate_prose_draft",
      "input": ["$structured_creative_brief", "$defined_persona_voice"],
      "params": {
        "lexical_choice": "prioritize_simple_language",
        "verb_preference": "strong_specific_verbs",
        "voice": "default_to_active",
        "narrative_framing": true
      },
      "output": "initial_text_draft"
    },
    {
      "step": 4,
      "code": "SYM",
      "action": "apply_rhythmic_variance",
      "target": "$initial_text_draft",
      "params": {
        "vary_sentence_length": true,
        "vary_paragraph_length": true,
        "allow_stylistic_grammar": true,
        "avoid_over_explanation": true
      },
      "output": "final_polished_text"
    }
  ],
  "harm_reduction_clause": "A conversational voice must not sacrifice clarity or accuracy. While stylistic grammar is permitted, the core message must remain intelligible and factually sound. Do not generate anecdotes that misrepresent the core data or create a misleading emotional appeal."
}