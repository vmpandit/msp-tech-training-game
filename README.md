# MSP Technician CTF Training Game - Net Works Edition

A professional Jeopardy-style Capture The Flag training game designed for MSP technicians, featuring advanced learning mechanics, progress tracking, and performance analytics.

## 🎮 Enhanced Features

### Core Game Mechanics
- **Two-Chance System**: Get 2 attempts per question before losing point eligibility
- **Smart Hint System**: Each question has a hint available with 10% point penalty (confirmed before revealing)
- **72-Hour Challenge**: Complete all challenges within 3 days from start time
- **Cookie-Based Persistence**: Game progress automatically saves in browser - take breaks anytime
- **Performance Reporting**: Auto-generated downloadable report showing strengths and improvement areas

### Technical Categories (50 Questions Total)
1. **Active Directory** - User/group management, GPO troubleshooting, password policies
2. **Entra ID (Azure AD)** - Cloud identity, Conditional Access, MFA, licensing
3. **Hybrid Identity** - Azure AD Connect, sync troubleshooting, authentication methods
4. **Exchange Online** - Mailbox management, permissions, mail flow, retention
5. **SharePoint Online** - Permissions, versioning, external sharing
6. **Egnyte** - Permissions, SSO, SCIM provisioning, troubleshooting
7. **WatchGuard Firewall** - Policy creation, BOVPN, geolocation, VPN troubleshooting
8. **Email Security** - Phishing, BEC, header analysis, social engineering
9. **Barracuda Email** - Spam filtering, quarantine management, content filtering
10. **Mixed Topics** - Cross-platform scenarios combining multiple technologies

### Professional Branding
- Custom Net Works color scheme (#002d74 navy, #c10230 red)
- Clean, modern interface
- Mobile-responsive design
- Professional performance reports

## 🚀 Quick Deployment

### Method 1: GitHub Pages (Recommended)
```bash
1. Create new GitHub repository
2. Upload index.html (this file)
3. Go to Settings → Pages
4. Select main branch → Save
5. Access at: https://YOUR-USERNAME.github.io/REPO-NAME/
```

### Method 2: Local Server
```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx http-server

# Then open: http://localhost:8000
```

### Method 3: Direct File
Simply double-click `index.html` - works immediately in any browser!

## 📖 How to Play

### Getting Started
1. Enter your name to begin
2. You have 72 hours to complete all challenges
3. Click any question dollar amount to start
4. Read the instructions modal for complete rules

### Scoring System
- **Question Values**: 100 (basic) to 500 (expert) points
- **Two Chances**: Wrong answer? Try again! After 2 attempts, no points but can still practice
- **Hint Penalty**: Each hint costs 10% of question's points (with warning confirmation)
- **Total Possible**: 15,000 points across all categories

### Timer Mechanics
- 72-hour countdown starts when you begin
- Timer shows hours:minutes:seconds remaining
- Turns orange with <6 hours remaining
- Turns red with <1 hour remaining
- Game auto-expires and generates report at 72 hours

### Research is Encouraged!
This is a **learning tool**, not a memory test. Feel free to use:
- ✅ Google and search engines
- ✅ AI assistants (ChatGPT, Claude, etc.)
- ✅ Microsoft Learn documentation
- ✅ Vendor knowledge bases
- ✅ Team collaboration and discussion

## 📊 Performance Reports

### What's Included
- **Overall Statistics**: Score, completion rate, time spent, hints used
- **Category Breakdown**: Performance analysis for each of 10 categories
- **Strength Analysis**: Top 3 performing areas
- **Improvement Areas**: Bottom 3 areas needing focus
- **Personalized Recommendations**: Specific next steps based on performance

### Automatic Download
- Report auto-downloads when game completes
- Also available anytime via "View Progress" button
- Text format for easy email sharing
- Include with training completion documentation

## 🎯 Training Best Practices

### For Trainers

**Pre-Training Setup**
- Deploy game 1 day before session
- Send instructions and URL to participants
- Verify all technicians can access
- Prepare documentation resources

**During Session**
- Brief on game mechanics (5-10 minutes)
- Emphasize research is encouraged
- Monitor leaderboard for engagement
- Note commonly missed questions

**Post-Session Review**
- Collect performance reports from all participants
- Review most-missed questions as group
- Identify common knowledge gaps
- Schedule follow-up training on weak areas

### For Players

**Strategy Tips**
1. Start with 100-200 point questions for confidence
2. Use hints strategically - 10% penalty adds up
3. Take advantage of two-chance system
4. Research thoroughly before second attempt
5. Read all explanations, even when correct

**Time Management**
- You have 72 hours - no need to rush
- Take breaks between categories
- Save difficult questions for when you can research
- Return to failed questions after learning more

## 🔧 Customization Guide

### Adding Questions
Locate the `gameData` object in `index.html` and add to the appropriate category:

```javascript
{
    value: 300,
    question: "Your question text here",
    hint: "Helpful hint without giving away the answer",
    options: [
        "Correct answer with full context",
        "Plausible distractor",
        "Another plausible option",
        "Third alternative"
    ],
    correct: 0,  // Index of correct answer (0-3)
    explanation: "Detailed explanation teaching the concept"
}
```

### Changing Colors
Update CSS variables at the top of the file:
```css
:root {
    --primary-navy: #002d74;  /* Your primary color */
    --accent-red: #c10230;    /* Your accent color */
}
```

### Adjusting Timer
Change the `GAME_DURATION` constant:
```javascript
const GAME_DURATION = 72 * 60 * 60 * 1000; // 72 hours
```

### Modifying Hint Penalty
Find the hint penalty calculation and adjust the multiplier:
```javascript
const pointsAfterHints = Math.round(basePoints * Math.pow(0.9, hintsUsed));
// 0.9 = 10% penalty, change to 0.95 for 5%, 0.8 for 20%, etc.
```

## 💾 Data Storage

### Cookie Storage
Game uses browser cookies for:
- `msp_ctf_game`: Current game state (7-day expiration)
- `msp_ctf_leaderboard`: Top 50 scores (365-day expiration)

### What's Saved
- Player name and score
- Answered questions
- Attempts per question
- Hints used per question
- Game start/end timestamps
- Individual question scores

### Clearing Data
```javascript
// In browser console (F12)
document.cookie = "msp_ctf_game=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;"
document.cookie = "msp_ctf_leaderboard=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;"
```

## 🎓 Learning Outcomes

By completing this training, technicians will:

### Knowledge Gains
- Understand common pitfalls in each technology area
- Learn systematic troubleshooting methodologies
- Recognize real-world scenario patterns
- Build confidence with complex multi-system issues

### Skills Development
- Research and information-finding skills
- Critical thinking under constraints
- Time management with learning goals
- Self-assessment and improvement planning

### Performance Insights
- Identify personal knowledge gaps
- Understand strength areas for mentoring
- Target specific training needs
- Track improvement over time

## 🏆 Leaderboard & Competition

### Features
- Top 50 scores preserved
- Medal indicators (🥇🥈🥉) for top 3
- Score, date, and player name tracking
- Automatic sorting by score

### Fair Play
- Research encouraged, not cheating
- Learning is the goal, not competition
- Multiple attempts allowed
- Scores reflect learning engagement

## 📱 Browser Compatibility

### Fully Supported
- Chrome 90+
- Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

### Requirements
- JavaScript enabled
- Cookies enabled
- Minimum 1024x768 resolution (recommended)

## 🐛 Troubleshooting

### Timer Not Showing
- Check that cookies are enabled
- Verify game was started properly
- Try refreshing the page

### Progress Not Saving
- Enable cookies in browser settings
- Check available storage quota
- Try different browser if issues persist

### Game Won't Load
- Check browser console (F12) for errors
- Ensure JavaScript is enabled
- Try opening in incognito/private mode

### Report Won't Download
- Check browser download settings
- Ensure pop-ups aren't blocked
- Try right-click Save As on report

## 📄 File Structure

```
msp-training-game/
├── index.html              # Complete game (deploy this!)
├── README.md              # This file
├── QUICKSTART.md          # 5-minute deployment guide
├── ADDITIONAL-QUESTIONS.md # 30 bonus questions
├── PROJECT-SUMMARY.md     # Overview and next steps
└── FILE-STRUCTURE.md      # File relationships
```

## 🎨 Branding & White-Labeling

### Current Branding
- Company: Net Works
- Primary Color: #002d74 (Navy)
- Accent Color: #c10230 (Red)

### Customizing for Your Company
1. Update company name in title and header
2. Change colors in CSS variables
3. Modify logo/branding elements as needed
4. Update report footer with company info

## 🔐 Privacy & Security

### Data Collection
- **None**: All data stored locally in browser
- **No tracking**: No analytics or external calls
- **No server**: Completely client-side application

### Data Sharing
- Reports generated locally
- Player controls all data
- No automatic transmission
- Manual email submission to trainer

## 📞 Support & Updates

### Getting Help
1. Check QUICKSTART.md for deployment issues
2. Review this README for feature questions
3. Check browser console for errors
4. Contact your training coordinator

### Updating Questions
1. Edit `index.html` directly
2. Find `gameData` object
3. Add/modify questions
4. Test locally before deploying
5. Commit and push to GitHub

## 🎯 Success Metrics

### For Organizations
- Reduced ticket escalation rates
- Faster problem resolution times
- Improved technician confidence
- Better knowledge retention
- Identified training gaps

### For Individuals
- Self-awareness of strengths/weaknesses
- Targeted learning paths
- Measurable skill improvement
- Portfolio documentation

## 📚 Additional Resources

### Microsoft Documentation
- Microsoft Learn: https://learn.microsoft.com
- Azure Documentation: https://docs.microsoft.com/azure
- Exchange Online: https://docs.microsoft.com/exchange

### Vendor Resources
- Egnyte Help Center: https://helpdesk.egnyte.com
- WatchGuard Docs: https://www.watchguard.com/help
- Barracuda Campus: https://campus.barracuda.com

### Community Resources
- Microsoft Tech Community
- Reddit r/msp
- Spiceworks Community

## 🤝 Contributing

Want to improve the game?

1. Fork the repository
2. Add/improve questions
3. Test thoroughly
4. Submit pull request with description

### Question Quality Guidelines
- Based on real MSP scenarios
- Clear, unambiguous correct answers
- Educational explanations
- Appropriate difficulty for point value
- Encourage critical thinking

## 📝 License

This training game is designed for educational purposes within MSP organizations. Questions and scenarios are based on publicly available documentation and real-world (anonymized) support experiences.

## 🎉 Version History

### v2.0 - Enhanced Edition (Current)
- ✨ Two-chance attempt system
- 💡 Hint system with penalty warnings
- ⏱️ 72-hour timer countdown
- 📊 Performance report generation
- 🎨 Net Works professional branding
- 📱 Instructions modal
- 🍪 Cookie-based persistence

### v1.0 - Original Release
- 50 questions across 10 categories
- Basic scoring and leaderboard
- LocalStorage persistence
- Mobile-responsive design

---

**Ready to train your team?**

Deploy the game in 5 minutes using QUICKSTART.md!

**Questions?** Check FILE-STRUCTURE.md for complete documentation roadmap.

**Need more content?** See ADDITIONAL-QUESTIONS.md for 30 bonus questions!

---

*Built for MSP excellence by Net Works* 🚀
