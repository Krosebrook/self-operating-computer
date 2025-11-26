# Self-Operating Computer - Use Cases & Scenarios

This document provides detailed real-world use cases and scenarios for the Self-Operating Computer Framework.

---

## Table of Contents

1. [Use Case 1: Automated Web Research & Data Collection](#use-case-1-automated-web-research--data-collection)
2. [Use Case 2: UI/UX Testing & Quality Assurance](#use-case-2-uiux-testing--quality-assurance)
3. [Use Case 3: Repetitive Desktop Task Automation](#use-case-3-repetitive-desktop-task-automation)
4. [Use Case 4: Content Creation & Social Media Management](#use-case-4-content-creation--social-media-management)
5. [Use Case 5: Local Application Automation & System Administration](#use-case-5-local-application-automation--system-administration)

---

## Use Case 1: Automated Web Research & Data Collection

**Problem:** Manual web research is time-consuming and requires visiting multiple websites, extracting information, and compiling results.

**Solution:** Use the Self-Operating Computer to automate multi-step web research workflows that require visual understanding and navigation.

### Scenario 1.1: Competitive Analysis

**Objective:**
```bash
operate -m gpt-4-with-ocr
> "Research top 5 competitors for project management software,
   capture pricing tables, and compile feature comparisons"
```

**Automated Steps:**
1. Opens browser and searches "best project management software 2025"
2. Identifies top results (Asana, Monday.com, ClickUp, Notion, Jira)
3. Visits each website's pricing page
4. Takes screenshots of pricing tiers
5. Navigates to features pages
6. Compiles information in a document

**Expected Results:**
- 5 competitor websites researched
- Pricing screenshots saved
- Feature comparison matrix created
- Total time: ~15 minutes (vs. 1+ hour manually)

**Best Practices:**
- Use `gpt-4-with-ocr` mode for reliable text-based navigation
- Provide specific competitor names if known
- Break into smaller tasks if too complex (e.g., "Research Asana pricing")

**Real-World Applications:**
- Market research teams analyzing competitive landscape
- Product managers validating pricing strategies
- Business analysts preparing competitor reports

**Limitations:**
- May struggle with JavaScript-heavy dynamic content
- CAPTCHA challenges will block progress
- Requires stable internet connection
- Website structure changes may cause failures

---

### Scenario 1.2: Academic Research Aggregation

**Objective:**
```bash
operate
> "Search Google Scholar for papers on 'multimodal AI computer control',
   download top 10 PDFs, and extract abstracts"
```

**Automated Steps:**
1. Opens Google Scholar
2. Enters search query in search field
3. Identifies relevant papers sorted by citations
4. For each of top 10 results:
   - Clicks PDF link when available
   - Saves file with descriptive name
   - Opens PDF and extracts abstract section
5. Compiles all abstracts into summary document

**Expected Results:**
- 10 academic papers downloaded
- Abstracts extracted and compiled
- Sources properly cited
- Total time: ~20 minutes (vs. 2+ hours manually)

**Best Practices:**
- Specify exact number of papers needed
- Use institutional access if behind paywalls
- Provide keywords for better search results

**Real-World Applications:**
- Researchers conducting literature reviews
- Graduate students preparing thesis background
- Scientists staying current with latest publications

---

## Use Case 2: UI/UX Testing & Quality Assurance

**Problem:** Manual UI testing is repetitive, error-prone, and difficult to scale across different user flows.

**Solution:** Automate visual testing workflows that require understanding UI state and user interactions.

### Scenario 2.1: E-commerce Checkout Flow Testing

**Objective:**
```bash
operate -m gpt-4-with-ocr
> "Test the checkout flow on staging.mystore.com:
   add product to cart, proceed to checkout,
   fill shipping info, and verify order summary"
```

**Automated Steps:**
1. Navigates to staging.mystore.com
2. Identifies product card and clicks "Add to Cart"
3. Verifies cart badge updates (visual confirmation)
4. Clicks "Checkout" button
5. Fills shipping form using OCR to find fields:
   - Name: "Test User"
   - Address: "123 Test St"
   - Email: "test@example.com"
   - Phone: "555-0100"
6. Proceeds to payment step
7. Verifies order summary shows correct:
   - Product name
   - Quantity
   - Price
   - Shipping address
8. Takes screenshot for QA documentation
9. Reports success or specific errors encountered

**Expected Results:**
- Complete checkout flow validated
- Screenshots of each step saved
- Pass/fail report generated
- Total time: ~3 minutes (vs. 10 minutes manually)

**Advantages Over Traditional Testing:**

| Feature | Selenium/Playwright | Self-Operating Computer |
|---------|-------------------|-------------------------|
| Selector brittleness | ❌ Breaks on DOM changes | ✅ Adapts automatically |
| Visual verification | ❌ Requires manual coding | ✅ Built-in visual understanding |
| Setup complexity | ❌ Need technical knowledge | ✅ Natural language objectives |
| Maintenance | ❌ High (update selectors) | ✅ Low (AI adapts) |

**Best Practices:**
- Use test data that won't affect production
- Run on staging environment
- Specify expected outcomes for verification
- Save screenshots for bug reports

**Real-World Applications:**
- QA engineers automating regression tests
- Development teams validating UI changes
- E-commerce platforms testing critical flows

---

### Scenario 2.2: Accessibility Audit

**Objective:**
```bash
operate
> "Navigate myapp.com using only keyboard controls,
   verify all interactive elements are reachable without mouse"
```

**Automated Steps:**
1. Opens myapp.com in browser
2. Uses only keyboard navigation:
   - Tab key to move between elements
   - Enter to activate buttons
   - Arrow keys for dropdowns
   - Space for checkboxes
3. Attempts to reach all interactive elements
4. Documents elements that aren't keyboard-accessible
5. Identifies missing focus indicators
6. Generates accessibility violation report with screenshots

**Expected Results:**
- Complete keyboard navigation audit
- List of inaccessible elements
- WCAG compliance report
- Total time: ~10 minutes (vs. 30 minutes manually)

**Best Practices:**
- Specify WCAG level (A, AA, AAA)
- Test with different keyboard layouts
- Combine with screen reader testing

**Real-World Applications:**
- Accessibility teams ensuring compliance
- Legal departments avoiding ADA lawsuits
- UX designers improving usability

---

## Use Case 3: Repetitive Desktop Task Automation

**Problem:** Many desktop workflows are too complex for simple scripts but too tedious to do manually.

**Solution:** Automate repetitive tasks that require human-like visual understanding and decision-making.

### Scenario 3.1: Bulk Invoice Processing

**Objective:**
```bash
operate -m gpt-4-with-ocr
> "Open all PDFs in ~/Invoices folder,
   extract invoice number, date, and total amount,
   enter data into invoices.xlsx spreadsheet"
```

**Automated Steps:**
1. Opens Finder (macOS) or Explorer (Windows)
2. Navigates to ~/Invoices directory
3. Identifies all PDF files in folder
4. For each PDF:
   - Opens file in default PDF viewer
   - Uses OCR to extract text content
   - Identifies invoice number (pattern: INV-XXXX)
   - Identifies date (various formats handled)
   - Identifies total amount (looks for "Total:", "Amount Due:")
   - Switches to invoices.xlsx in Excel
   - Finds next empty row
   - Enters extracted data in columns:
     - Column A: Invoice Number
     - Column B: Date
     - Column C: Amount
   - Closes PDF
5. Saves Excel file
6. Reports: "Processed 47 invoices successfully"

**Expected Results:**
- All invoices processed and data extracted
- Excel spreadsheet populated with structured data
- Error report for any unparseable invoices
- Total time: ~15 minutes for 50 invoices (vs. 100 minutes manually)

**Time Savings Analysis:**
```
Manual process: 2 minutes per invoice
- Open PDF: 10s
- Read and identify fields: 60s
- Enter into Excel: 40s
- Close and next: 10s

Automated process: ~20 seconds per invoice
- OCR extraction: 5s
- Data entry: 5s
- Navigation: 10s

50 invoices:
Manual: 100 minutes
Automated: 17 minutes
Savings: 83 minutes (83% reduction)
```

**Best Practices:**
- Ensure PDFs are text-based (not scanned images)
- Use consistent file naming convention
- Have template Excel file ready
- Review first few entries for accuracy

**Real-World Applications:**
- Accounting teams processing vendor invoices
- Finance departments reconciling expenses
- Small businesses without ERP systems

---

### Scenario 3.2: Software Installation & Configuration

**Objective:**
```bash
operate
> "Download and install VSCode, then install extensions:
   Python, ESLint, Prettier, GitLens, and Docker"
```

**Automated Steps:**
1. Opens browser and searches "VSCode download"
2. Identifies official download link (code.visualstudio.com)
3. Detects operating system and clicks correct download
4. Waits for download completion (monitors Downloads folder)
5. Opens installer package
6. Clicks through installation wizard:
   - Accept license agreement
   - Choose installation location
   - Select additional tasks (add to PATH, etc.)
   - Click "Install"
7. Waits for installation to complete
8. Launches VSCode application
9. Opens Extensions panel (Cmd+Shift+X or Ctrl+Shift+X)
10. For each extension:
    - Types extension name in search
    - Identifies correct extension by publisher
    - Clicks "Install" button
    - Waits for installation complete
11. Configures settings:
    - Opens settings (Cmd+,)
    - Enables "Format on Save"
    - Sets default formatter to Prettier
    - Saves settings
12. Verifies all extensions installed and active
13. Reports: "VSCode installed with 5 extensions configured"

**Expected Results:**
- VSCode installed and launched
- All 5 extensions installed and activated
- Recommended settings configured
- Total time: ~8 minutes (vs. 20 minutes manually)

**Best Practices:**
- Provide specific extension names (avoid ambiguity)
- Specify configuration preferences upfront
- Test on clean system first
- Document any manual steps required (license keys, etc.)

**Real-World Applications:**
- IT departments onboarding new developers
- DevOps teams standardizing development environments
- Educators setting up student workstations
- Individual developers automating laptop setup

---

## Use Case 4: Content Creation & Social Media Management

**Problem:** Posting content across multiple social platforms is time-consuming and requires navigating different UIs.

**Solution:** Automate content distribution workflows without needing API access to each platform.

### Scenario 4.1: Multi-Platform Social Posting

**Objective:**
```bash
operate -m gpt-4-with-ocr --voice
> [Speaking] "Post announcement 'New product launch next week!
   Visit mysite.com for details' to Twitter, LinkedIn,
   and Facebook with the image product_announcement.png"
```

**Automated Steps:**

**Twitter/X:**
1. Opens twitter.com and logs in (if needed)
2. Clicks "Post" or "What's happening?" field
3. Types announcement text
4. Clicks image upload button (🖼️ icon)
5. Selects product_announcement.png from file picker
6. Waits for image upload
7. Verifies preview looks correct
8. Clicks "Post" button
9. Waits for confirmation

**LinkedIn:**
1. Opens linkedin.com
2. Clicks "Start a post" at top of feed
3. Types announcement with professional tone:
   ```
   Exciting news! We're launching our new product next week.

   Learn more at mysite.com

   #ProductLaunch #Innovation #Technology
   ```
4. Clicks "Add media" button
5. Uploads product_announcement.png
6. Adds relevant hashtags
7. Clicks "Post"
8. Confirms successful posting

**Facebook:**
1. Opens facebook.com
2. Navigates to business page (if applicable)
3. Clicks "Create post" in publisher
4. Enters announcement text
5. Clicks "Photo/Video" to upload image
6. Selects product_announcement.png
7. Optionally schedules post or posts immediately
8. Clicks "Post"
9. Verifies post appears on page

**Final Report:**
```
✅ Posted to Twitter/X successfully
✅ Posted to LinkedIn successfully
✅ Posted to Facebook successfully

Total reach: ~5,000 followers across platforms
Time: 5 minutes (vs. 15 minutes manually)
```

**Advantages Over Social Media Management Tools:**

| Feature | Buffer/Hootsuite | Self-Operating Computer |
|---------|------------------|-------------------------|
| API required | ✅ Yes (limited free tier) | ❌ No API needed |
| Platform coverage | ⚠️ Major platforms only | ✅ Any visual interface |
| 2FA handling | ❌ Complex setup | ✅ Handles like human |
| Cost | 💰 $15-99/month | 💰 API costs only |
| Custom workflows | ❌ Limited | ✅ Fully customizable |

**Best Practices:**
- Keep images under 5MB for faster upload
- Tailor message tone for each platform
- Verify login sessions before running
- Check post preview before publishing
- Monitor for error messages (rate limits, etc.)

**Real-World Applications:**
- Social media managers coordinating campaigns
- Marketing teams announcing product launches
- Small businesses with limited budget
- Influencers managing personal brand

---

### Scenario 4.2: YouTube Video Upload Automation

**Objective:**
```bash
operate -m gpt-4-with-ocr
> "Upload video ~/Videos/tutorial_05.mp4 to YouTube with title
   'Python Tutorial #5: Functions and Scope',
   description from description.txt,
   tags 'python, tutorial, programming, functions',
   and thumbnail custom_thumb.png"
```

**Automated Steps:**
1. Opens youtube.com and navigates to YouTube Studio
2. Clicks "Create" button → "Upload video"
3. Clicks file selector or drag-drop area
4. Navigates to ~/Videos/ and selects tutorial_05.mp4
5. Waits for upload to begin (progress bar appears)
6. While uploading, fills out video details:

   **Details Tab:**
   - Title field: "Python Tutorial #5: Functions and Scope"
   - Description: Reads from description.txt and pastes content
   - Thumbnail: Clicks "Upload thumbnail" → selects custom_thumb.png
   - Playlist: Selects "Python Tutorial Series" (if exists)
   - Audience: Selects "No, it's not made for kids"

   **More Options:**
   - Tags: Enters "python, tutorial, programming, functions"
   - Category: Selects "Education"
   - Comments: Enables comments
   - Age restriction: None

7. Clicks "Next" to proceed through wizard:
   - Monetization: (Skips or configures if enabled)
   - Video elements: (Skips end screens for now)
   - Checks: Waits for automatic checks to complete

8. **Visibility:**
   - Selects "Public" (or "Scheduled" with date/time)
   - Clicks "Publish" or "Schedule"

9. Waits for processing to complete
10. Copies video URL from confirmation page
11. Reports: "Video published successfully at youtube.com/watch?v=ABC123xyz"

**Expected Results:**
- Video uploaded and published
- All metadata correctly set
- Custom thumbnail applied
- Added to playlist
- Total time: ~10 minutes + upload time (vs. 20 minutes manually)

**Best Practices:**
- Prepare description.txt with full formatting
- Use 1280x720 thumbnails (JPEG, under 2MB)
- Schedule posts for optimal timing
- Double-check title for typos (AI may misread)
- Save video URL to tracking spreadsheet

**Real-World Applications:**
- Content creators automating upload workflow
- Educational channels publishing course content
- Marketing teams distributing video campaigns
- Agencies managing multiple client channels

**Advanced Variations:**
```bash
# Batch upload entire series
operate
> "Upload all videos in ~/Tutorials/Season2/ to YouTube,
   use filename for title, auto-generate tags,
   add to 'Season 2' playlist, schedule daily at 9 AM"

# Cross-post to Vimeo
operate
> "Upload tutorial_05.mp4 to both YouTube and Vimeo
   with platform-specific descriptions"
```

---

## Use Case 5: Local Application Automation & System Administration

**Problem:** Many desktop applications and system tasks lack CLI or API access, requiring manual GUI interaction.

**Solution:** Automate GUI-based workflows for applications that don't provide programmatic interfaces.

### Scenario 5.1: Database Backup via GUI Tool

**Objective:**
```bash
operate -m gpt-4-with-ocr
> "Open MySQL Workbench, connect to production database,
   export 'customers' table to ~/backups/customers_2025-11-26.sql"
```

**Automated Steps:**
1. Launches MySQL Workbench:
   - macOS: Cmd+Space → types "MySQL Workbench" → Enter
   - Windows: Win key → types "MySQL Workbench" → Enter

2. Waits for application to load (identifies welcome screen)

3. Identifies saved connection "Production DB" in connections panel

4. Double-clicks connection to initiate connection

5. Handles authentication:
   - Enters password from system keychain (if prompted)
   - Or uses saved credentials
   - Clicks "Connect"

6. Waits for connection to establish (looks for "Connected" status)

7. Navigates schema tree in left sidebar:
   - Expands "Schemas" section
   - Finds production database
   - Expands "Tables" folder
   - Locates "customers" table

8. Exports table:
   - Right-clicks "customers" table
   - Hovers over "Table Data Export Wizard"
   - Clicks "Export to Self-Contained File"

9. Configures export settings:
   - Format: SQL INSERT statements
   - Output file: ~/backups/customers_2025-11-26.sql
   - Include CREATE TABLE: Yes
   - Include DROP TABLE: No
   - Extended inserts: Yes (for faster restore)

10. Clicks "Start Export" button

11. Monitors progress bar until completion

12. Verifies export:
    - Checks file exists at ~/backups/
    - Verifies file size > 0 bytes
    - Reads first few lines to confirm valid SQL

13. Reports:
    ```
    ✅ Backup completed successfully
    File: ~/backups/customers_2025-11-26.sql
    Size: 2.3 MB
    Rows: ~15,000 records
    Duration: 45 seconds
    ```

**Expected Results:**
- Database table exported to SQL file
- Backup saved with dated filename
- File integrity verified
- Total time: ~2 minutes (vs. 5 minutes manually)

**Best Practices:**
- Use read-only connection for safety
- Schedule daily backups with cron/Task Scheduler
- Compress large exports (add `.gz` extension)
- Test restore process periodically
- Rotate old backups (keep last 30 days)

**Real-World Applications:**
- Database administrators automating backups
- DevOps teams implementing DR strategies
- Small businesses without backup software
- Developers creating data snapshots before migrations

**Advanced Variations:**
```bash
# Backup all tables
operate
> "Export all tables from production database to
   ~/backups/full_backup_2025-11-26/, one file per table"

# Backup to cloud storage
operate
> "Backup customers table, then upload the SQL file
   to Google Drive in the 'DB Backups' folder"

# Automated weekly backup
# (Combined with cron job)
0 2 * * 0 /usr/local/bin/operate -m gpt-4-with-ocr \
  --prompt "Backup all tables from production DB"
```

---

### Scenario 5.2: System Monitoring Dashboard Check

**Objective:**
```bash
operate
> "Open monitoring dashboard at http://grafana.internal,
   check CPU and memory metrics for server-prod-01,
   take screenshot if any metric exceeds 80%,
   send email alert to ops-team@company.com"
```

**Automated Steps:**
1. Opens web browser (or uses existing window)

2. Navigates to http://grafana.internal

3. Handles authentication:
   - Logs in via SSO (clicks "Sign in with Google")
   - Or enters username/password if needed

4. Waits for dashboard to load

5. Navigates to correct dashboard:
   - Clicks "Dashboards" menu
   - Searches for "Infrastructure Overview"
   - Clicks dashboard link

6. Applies server filter:
   - Finds dropdown labeled "Server"
   - Clicks to expand options
   - Selects "server-prod-01"
   - Waits for metrics to refresh

7. Reads metrics using OCR:
   - **CPU Gauge**: Identifies gauge widget
     - Reads value: "CPU: 73%"
     - Status: Normal (< 80%)

   - **Memory Gauge**: Identifies gauge widget
     - Reads value: "Memory: 89%"
     - Status: ⚠️ High (> 80%)

   - **Disk Gauge**:
     - Reads value: "Disk: 45%"
     - Status: Normal

   - **Network Graph**:
     - Identifies trend (stable/increasing)

8. Detects threshold violation (Memory > 80%)

9. Takes screenshot:
   - Uses built-in screenshot function
   - Saves to /tmp/grafana_alert_2025-11-26_14-30.png
   - Crops to relevant dashboard area

10. Composes alert email:
    - Opens Mail app (Cmd+N for new message)
    - To: ops-team@company.com
    - Subject: "⚠️ High Memory Alert: server-prod-01"
    - Body:
      ```
      Alert triggered at 2:30 PM on Nov 26, 2025

      Server: server-prod-01
      Metric: Memory Usage
      Current Value: 89%
      Threshold: 80%

      Other Metrics:
      - CPU: 73% (Normal)
      - Disk: 45% (Normal)

      Dashboard: http://grafana.internal/d/infrastructure

      Please investigate and take action if necessary.
      ```
    - Attaches screenshot
    - Clicks "Send"

11. Logs alert to file:
    - Appends entry to ~/monitoring_alerts.log
    - Format: `2025-11-26 14:30:00 | server-prod-01 | Memory | 89%`

12. Reports:
    ```
    ⚠️ Alert detected and sent
    Server: server-prod-01
    Issue: Memory usage at 89% (threshold: 80%)
    Action: Email sent to ops-team@company.com
    Screenshot: /tmp/grafana_alert_2025-11-26_14-30.png
    ```

**Expected Results:**
- Dashboard checked and metrics evaluated
- Alert email sent with screenshot
- Log entry created for audit trail
- Total time: ~3 minutes (vs. manual check every hour)

**Best Practices:**
- Set realistic thresholds (avoid alert fatigue)
- Include trend graphs in screenshots
- Use specific subject lines for filtering
- Log all alerts for historical analysis
- Configure retry logic for transient failures

**Real-World Applications:**
- Site reliability engineers monitoring infrastructure
- Operations teams implementing proactive alerting
- DevOps automating on-call rotations
- Small teams without enterprise monitoring tools

**Advanced Variations:**
```bash
# Multi-server check
operate
> "Check all production servers (prod-01 through prod-05),
   create summary table of CPU/memory/disk,
   highlight any values >80% in red"

# Trend analysis
operate
> "Open Grafana, check server-prod-01 metrics,
   compare current values to 7-day average,
   alert if >20% deviation"

# Automated remediation
operate
> "Check memory on server-prod-01,
   if >90%, SSH to server and restart memory-intensive services,
   then verify memory drops below 70%"
```

---

## Additional Scenarios

### Scenario 6: Voice-Controlled Computer Operation

**Use Case:** Hands-free computing for accessibility or multitasking.

**Setup:**
```bash
# Install audio requirements
pip install -r requirements-audio.txt
brew install portaudio  # macOS

# Run with voice mode
operate --voice
```

**Example Interaction:**
```
[🎤 Microphone activated - Speak your objective]

User (speaking): "Open my email and archive all messages from last week"

[🔄 Transcribing with Whisper...]
[📝 Objective: Open my email and archive all messages from last week]

Steps:
1. Opens Mail app (Cmd+Space → "Mail")
2. Waits for inbox to load
3. Clicks search bar
4. Types filter: "date:last week"
5. Presses Enter to execute search
6. Identifies matching messages (23 found)
7. Presses Cmd+A to select all
8. Presses E or clicks "Archive" button
9. Verifies messages moved to archive
10. Reports: "Archived 23 messages from last week"

[✅ Task completed in 45 seconds]
```

**Real-World Applications:**
- Accessibility for users with mobility impairments
- Multitasking while cooking or exercising
- Voice-first workflows for efficiency
- Assistive technology for elderly users

---

## Best Practices Across All Use Cases

### 1. Objective Clarity
- ✅ **Good**: "Open Chrome, search for 'Python tutorial', click first result, take screenshot"
- ❌ **Bad**: "Find something about Python"

### 2. Model Selection

| Task Type | Recommended Model | Reason |
|-----------|------------------|--------|
| Text-heavy UI (forms, buttons) | `gpt-4-with-ocr` | Reliable text detection |
| Visual elements (images, charts) | `gpt-4o` or `claude-3` | Better visual understanding |
| Complex UI (many elements) | `gpt-4-with-som` | Set-of-Mark labeling |
| Cost-sensitive | `llava` (local) | No API costs |
| Voice input | Any + `--voice` | Whisper transcription |

### 3. Error Handling
```bash
# Include contingency plans
operate
> "Try to download file from website.com/file.pdf,
   if download fails, try alternative link at backup.com/file.pdf,
   if both fail, report error with screenshots"
```

### 4. Verification Steps
```bash
# Always verify critical actions
operate
> "Send email to client, then verify it appears in Sent folder"
```

### 5. Iteration Limits
```bash
# Complex tasks may hit 10-iteration limit
# Break into smaller objectives:

# Instead of:
operate > "Research competitors, create comparison table,
           email to team, update project board"

# Do:
operate > "Research competitors and create comparison table"
operate > "Email comparison table to team"
operate > "Update project board with research findings"
```

---

## Troubleshooting Common Issues

### Issue: "Operation failed - could not find element"
**Cause:** OCR couldn't locate the specified text
**Solution:**
- Use more specific text (e.g., "Submit Button" instead of "Submit")
- Switch to coordinate-based mode (`gpt-4o`)
- Verify element is visible on screen

### Issue: Task incomplete after 10 iterations
**Cause:** Hit maximum iteration limit
**Solution:**
- Break task into smaller objectives
- Simplify the workflow
- Use more specific instructions

### Issue: Incorrect text typed
**Cause:** OCR misread text or AI hallucination
**Solution:**
- Use `--verbose` mode to see AI reasoning
- Provide exact text in quotes
- Use `gpt-4.1-with-ocr` for better accuracy

### Issue: Security permissions error
**Cause:** macOS/Windows requires accessibility permissions
**Solution:**
- System Preferences → Security & Privacy → Accessibility
- Add Terminal app to allowed apps
- Restart terminal after granting permissions

---

## Cost Estimation

### API Costs per Use Case (Approximate)

| Use Case | Model | Est. Cost | Time Saved |
|----------|-------|-----------|------------|
| Web research (10 pages) | GPT-4o + OCR | $0.15 | 45 min |
| UI testing flow | GPT-4o + OCR | $0.08 | 7 min |
| Invoice processing (50) | GPT-4o + OCR | $0.25 | 83 min |
| Social media posting (3) | GPT-4o + OCR | $0.12 | 10 min |
| Database backup | GPT-4o + OCR | $0.05 | 3 min |

**Cost Breakdown:**
- GPT-4o with vision: ~$0.01-0.03 per iteration
- Claude 3 Opus: ~$0.015-0.04 per iteration
- Gemini Pro: ~$0.002-0.005 per iteration
- LLaVa (local): $0.00 (no API cost)

**Monthly Cost Scenarios:**

```
Light Usage (5 tasks/day):
- 150 tasks/month × $0.10 avg = $15/month
- Time saved: ~20 hours/month
- ROI: ~$400 value (at $20/hour)

Medium Usage (20 tasks/day):
- 600 tasks/month × $0.10 avg = $60/month
- Time saved: ~80 hours/month
- ROI: ~$1,600 value

Heavy Usage (100 tasks/day):
- 3,000 tasks/month × $0.10 avg = $300/month
- Time saved: ~400 hours/month
- ROI: ~$8,000 value (team of 5)
```

---

## Conclusion

The Self-Operating Computer Framework enables automation of workflows that were previously impossible to automate without human-like visual understanding. These use cases demonstrate applications across:

- 🔍 Research & data collection
- 🧪 Testing & quality assurance
- 🔄 Repetitive task automation
- 📱 Content & social media management
- 🖥️ System administration

**Key Advantages:**
- No API access required
- Adapts to UI changes
- Natural language control
- Cross-platform compatibility

**Important Considerations:**
- Review [AUDIT.md](AUDIT.md) for security implications
- Start with low-risk tasks
- Monitor API costs
- Verify critical operations manually

For more examples and community contributions, visit the [GitHub Discussions](https://github.com/OthersideAI/self-operating-computer/discussions).
