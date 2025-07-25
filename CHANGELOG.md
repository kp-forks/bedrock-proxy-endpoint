# Changelog
All notable changes to this project will be documented in this file.

## [2.4.1] - 2025-07-24
### Added
- Updated to use Bedrock Wrapper v2.4.1\
- Vision support for Claude 3 Haiku
- Support for Amazon Nova models:
  - Amazon Nova Micro (text-only, ultra-low latency)
  - Amazon Nova Lite (multimodal, low-cost)
  - Amazon Nova Pro (multimodal, high capability)

## [2.3.1] - 2025-05-28
### Added
- Updated to use Bedrock Wrapper v2.3.1
  - Support for Claude Sonnet 4
  - Support for Claude Opus 4

## [2.3.0] - 2025-02-27 - Claude Sonnet 3.7 + Vision
### Added
- Support for Claude Sonnet 3.7
- Support for Clause Sonnet 3.7 Thinking
- Support for Claude Sonnet 3.x Vision

## [2.2.0] - 2025-01-01 - Llama 3.3 70b
### Added
- Support for Llama 3.3 70b

## [2.1.0] - 2024-11-21 - Claude Haiku 3.5
### Added
- Support for "Anthropic Claude 3.5 Haiku"

## [2.0.0] - 2024-10-31 - Claude
### Added
- Updated to use Bedrock Wrapper v2.0.0
- Model support for:
  - Claude 3.5 Sonnet V2
  - Claude 3.5 Sonnet
  - Claude 3 Haiku
- Unstreamed response are returned as a string similar to streaming responses
    > Note: This could be a breaking change for any clients that are expecting a JSON response from unstreamed responses

## [1.0.9] - 2024-09-25 - Lamma 3.2
### Added
- Model support for:
  - Llama 3.2 1b
  - Llama 3.2 3b
  - Llama 3.2 11b
  - Llama 3.2 90b


## [1.0.7] - 2024-07-24 - Lamma 3.1
### Added
- Model support for:
  - Llama-3-1-8b
  - Llama-3-1-70b


## [1.0.3] - 2024-05-06 - Initial Stable Release
### Added
- OpenAI API compatible proxy endpoint for AWS Bedrock
- Support for HTTP and HTTPS servers
- IP-based rate limiting
- Environment variable configuration
- AWS IAM authentication via API key
- Streaming and non-streaming responses
- `/models` endpoint to list supported models
- Root info page with documentation
- Endpoint type
  - `/chat/completions`
- Model Support for:
  - Llama-3-8b
  - Llama-3-70b
  - Mistral-7b
  - Mixtral-8x7b
  - Mistral-Large
- Error handling middleware
- Console logging toggle

### Security
- HTTPS support with custom key and certificate paths
- Rate limiting configuration options
- AWS IAM authentication required for API access

### Documentation
- Installation instructions
- Configuration guide
- Authentication details
- Usage examples
- API endpoint documentation 
