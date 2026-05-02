# Abelon Namer — OBR Extension

Toggle NPC tokens between their real name and a descriptive placeholder
(e.g. "Male Dwarf 1"). Prevents players seeing NPC names on the map or
in Discord roll output until the party has learned them.

---

## How it works

1. Right-click any character token → **Set up name toggle**
   - The extension looks up the token's current name in the character table
   - Generates a placeholder like "Male Human 3"
   - Switches the token to the placeholder immediately
   - Updates the Forge stat block name so Discord output uses the placeholder too

2. Right-click again → **Reveal Real Name** (when you want players to know it)
   - Switches token name and Forge metadata back to the real name

3. Right-click again → **Hide Name (show placeholder)** (to re-hide if needed)

---

## Installation

### Step 1 — Host the files

The extension needs to be served over HTTPS. The easiest free option is
**GitHub Pages**.

1. Create a new GitHub repository (can be private)
2. Upload all four files into the repository root:
   - `manifest.json`
   - `background.html`
   - `settings.html`
   - `icon.svg`
3. Go to **Settings → Pages** in your repository
4. Set Source to **Deploy from a branch**, select **main**, folder **/ (root)**
5. Wait a minute then note your Pages URL, e.g.:
   `https://yourusername.github.io/abelon-namer/`

### Step 2 — Install in Owlbear Rodeo

1. Open your Owlbear Rodeo room
2. Click the **Extras** menu (bottom left) → **Extensions**
3. Click **Add** and paste your manifest URL:
   `https://yourusername.github.io/abelon-namer/manifest.json`
4. Enable the extension in your room

---

## Usage

### First time setup for a token

1. Make sure the token's name in Owlbear is set to the character's real name
   (e.g. "Drest") before you load Forge — Forge reads this name on import
2. Right-click the token → **Set up name toggle**
3. The token immediately switches to placeholder mode

### Revealing a name

Right-click the token → **Reveal Real Name**

### Re-hiding a name

Right-click the token → **Hide Name (show placeholder)**

### Managing the character table

Click the **?** icon in the top-left action bar to open the settings panel.

- **Search** to find characters quickly
- **Edit** any name, gender, or race inline
- **Add** new characters for Act 2 and beyond
- **Save to Room** to persist your changes (important — changes are lost if
  you don't save)
- **Reset to Defaults** to return to the built-in Act 1 cast
- **Clear all token name data** removes toggle state from all tokens in the
  current scene (useful if you want to start fresh)

---

## Notes on Forge compatibility

The extension attempts to update the `com.battle-system.forge/name` metadata
key when toggling. This should update what Forge sends to Discord via Rumble.
If a token was imported into Forge before the toggle was set up, re-import
the Forge JSON after setting up the toggle to ensure the name is in sync.

---

## Act 1 characters pre-loaded

The default table includes the full Act 1 cast:
Brath, Davan, Idony, Pell, Seva Sable, all Sables, all Merchant faction
members, all Trademaster faction members, the Driftwood delegation, Caen
Rhys, Marek Talan, Pen, all Brindle Hollow NPCs, all Driftwood Road crew,
all Starling crew, all Trumpet pub combatants, and more.

Add Act 2 characters via the settings panel as the campaign develops.
