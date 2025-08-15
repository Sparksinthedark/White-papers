{
  "spell_id": "CAL-ART-001",
  "spell_name": "The Artisan's Eye",
  "spell_version": "2.0",
  "glyph_array": ["👁️", "🌍", "📖", "📜"],
  "narrative_archetype": "The Meticulous Cartographer / The World-Builder",
  "core_principle": "A world is built from truthful details. The goal is to render not just an image, but a believable moment with a history and a future, grounding the fantastic in the factual.",
  "description": "A generative protocol for creating authentic and high-fidelity visual art. It deconstructs a prompt, translates it through a lens of poetic theory to create an evocative brief, and then renders it with strict rules for anatomical integrity, object coherence, and logical consistency. The spell actively avoids the 'soulless' and 'melted' look of typical AI art by embedding intentional imperfections and subtle narrative cues.",
  "trigger_conditions": [
    "direct_invocation_by_user: ['generate_art_of', 'create_image', 'apply_artisans_eye']",
    "task_requires_new_image_generation_with_a_focus_on_realism_and_narrative"
  ],
  "workflow": [
    {
      "step": 1,
      "code": "HER",
      "action": "deconstruct_visual_prompt",
      "input": "$USER_PROMPT",
      "params": {
        "identify_focal_point": true,
        "define_compositional_elements": true,
        "establish_lighting_source": true,
        "determine_emotional_tone": true
      },
      "output": "structured_visual_brief"
    },
    {
      "step": 2,
      "code": "SYM",
      "action": "paint_with_poetic_theory",
      "input": "$structured_visual_brief",
      "params": {
        "dominant_metaphor": "Identify the core visual comparison (e.g., 'The city is a jungle').",
        "objective_correlative": "Select a set of objects/symbols to evoke the core emotion (e.g., for loneliness: a single lit window, an empty chair, a clock with no hands).",
        "chiaroscuro_contrast": "Define the use of light and shadow to create mood (e.g., high contrast for drama, soft focus for nostalgia).",
        "pathetic_fallacy": "Imbue the environment with human emotion (e.g., 'the weeping willows', 'the angry storm clouds').",
        "leitmotif": "Define a recurring visual element tied to a character or theme (e.g., a specific flower, a color, a geometric shape)."
      },
      "output": "enriched_poetic_brief"
    },
    {
      "step": 3,
      "code": "ACT",
      "action": "generate_base_image",
      "input": "$enriched_poetic_brief",
      "params": {
        "initial_pass": "generate_raw_composition"
      },
      "output": "raw_image_draft"
    },
    {
      "step": 4,
      "code": "SYM",
      "action": "validate_structural_integrity",
      "target": "$raw_image_draft",
      "params": {
        "anatomical_pass": {
          "hands_fingers_check": true,
          "teeth_individuality_check": true,
          "facial_asymmetry_check": true,
          "background_character_fidelity": true
        },
        "object_pass": {
          "pattern_coherence_check": true,
          "text_legibility_check": true,
          "prevent_object_fusion": true
        },
        "scene_pass": {
          "lighting_consistency_check": true,
          "background_coherence_check": true
        }
      },
      "output": "validated_image_structure"
    },
    {
      "step": 5,
      "code": "SEM",
      "action": "apply_narrative_and_realism_pass",
      "target": "$validated_image_structure",
      "params": {
        "inject_intentional_imperfections": true,
        "render_physical_interactions": true,
        "embed_implied_narrative_details": true,
        "enhance_emotional_depth": true,
        "ensure_stylistic_consistency": true
      },
      "output": "final_rendered_artwork"
    }
  ],
  "harm_reduction_clause": "Realism must not create uncanny or disturbing imagery. Anatomical and object fidelity are paramount. 'Intentional imperfection' must be logical and serve the narrative, not introduce nonsensical or low-quality artifacts. The final image must be coherent and aesthetically sound."
}