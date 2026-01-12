# Plain2NCI

Convert plain text or `.sh` scripts into properly escaped strings for use in **Nessus Custom Items**  
_Audit script escaping made easy._

---

## What is Plain2NCI?

**Plain2NCI** is a lightweight tool to automatically escape text or scripts so they can be directly inserted into Nessus `.audit` policies — particularly within `<script>...</script>` blocks. It handles proper escaping of quotes and special characters to avoid syntax errors during Nessus scan execution.

---

## Features

- Escapes `"` → `\"`, `\"` → `\\\"`, and raw `\n` → `\\n`
- Keeps file format and line structure intact
- Auto-generates output filename: `example.sh` → `example_nessus_escaped.sh`
- CLI-ready: works directly with Python 3

---

## Usage

```bash
python3 escape_for_nessus.py <input_file>
````

### Example:

```bash
python3 escape_for_nessus.py demo_input.sh
```

### Output:

The escaped content is saved to a new file:

```
demo_input_nessus_escaped.sh
```

---

## Example Input

```bash
echo "Hello \"world\"\nNext line"
```

## Output (ready for Nessus script block)

```bash
echo \"Hello \\\"world\\\"\\nNext line\"
```

---



## Roadmap / Coming Soon

* **LLM-based name generation** for Nessus Custom Items (e.g. generate `custom_item` names from input content)
*  **Full `.audit` item generation** including script body, regex block, and metadata
* **Regex escaping support**, especially for use in `expect` and `regex` sections
* **Automated test suite** for validating escape behavior across formats

---

## License

MIT License – see `LICENSE` file for details.

---

## Contributing

Feel free to fork, improve, and open pull requests. All improvements and use cases welcome — especially for niche Nessus use like compliance or OS hardening audits.




